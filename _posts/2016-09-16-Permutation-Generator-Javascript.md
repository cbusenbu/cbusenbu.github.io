---
layout: post
title: Permutation Generator in Javascript.
date: 2016-09-16
summary: Creating a permutation generator in Javascript based on Heap's Algorithm.
categories: Javascript permutation generator
---

This past week, I was assigned to create a sequence of permutations that would be able to 
handle a large amount of permutations. We are thinking greater than 10!. If we are required 
to create that many permutations, we can easily run into issues of memory being filled. 
Well thankfully permutations can be procedurally generated, meaning that we can create a new
permutation that has not been created yet based on a much smaller amount of memory.

I used [Heap's Algorithm](https://en.wikipedia.org/wiki/Heap%27s_algorithm)  to accomplish this,
Pretty simple to implement in Javascript, the thing to notice is that I have actually created a generator
within the permute function itself. This is purely from my decision to abstract out that piece.
My thought process was that I wanted the actual function of permute to be clean and simple. As we 
can see the only permutation that swapGenerator does not actually generate is the initial input. 
Hence, why we have an initial yield of letters, and then we yield the swapGenerator's values.

Again, this is not too difficult of material, but I have been asked to do permutations for 
a lot of assignments, and this is one of the simplest I have encountered.




```javascript
    function* permute(letters){
        function* swapGenerator(word){
            let arrayOfLetters = word.split("");
            let arrayOfInts = new Array(arrayOfLetters.length).fill(0);
            var i = 0;
            for(; i < arrayOfLetters.length;){
                if ( arrayOfInts[i] < i ){
                    if( i%2 == 0   ){
                        arrayOfLetters = swap(arrayOfLetters, 0, i);
                    }
                    else{
                        arrayOfLetters = swap(arrayOfLetters,arrayOfInts[i],i);
                    }
                    yield arrayOfLetters.join("");
                    arrayOfInts[i]+=1;
                    i = 0;
                }
                else{
                    arrayOfInts[i] = 0;
                    i++;
                }
            }
                                        
            function swap(array, indexOne, indexTwo){
                let temp = array[indexOne];
                array[indexOne] = array[indexTwo];
                array[indexTwo] = temp;

                return array;
            }
        }
                                
        yield letters;
        yield* swapGenerator(letters);
                                        
    }

```

