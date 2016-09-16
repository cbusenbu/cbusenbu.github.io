---
layout: post
title: Permutation Generator in Javascript.
date: 2016-09-16
summary: Creating a permutation generator in Javascript based on Heap's Algorithm.
categories: Javascript permutation generator
---

'''javascript
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

'''

