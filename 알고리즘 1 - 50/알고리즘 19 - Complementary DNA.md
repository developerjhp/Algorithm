# Q.
Deoxyribonucleic acid (DNA) is a chemical found in the nucleus of cells and carries the "instructions" for the development and functioning of living organisms.

If you want to know more: http://en.wikipedia.org/wiki/DNA

In DNA strings, symbols "A" and "T" are complements of each other, as "C" and "G". You have function with one side of the DNA (string, except for Haskell); you need to get the other complementary side. DNA strand is never empty or there is no DNA at all (again, except for Haskell).

More similar exercise are found here: http://rosalind.info/problems/list-view/ (source)

Example: (input: output)

DNAStrand ("ATTGC") // return "TAACG"
DNAStrand ("GTAT") // return "CATA"

# A)

```js
function DNAStrand(dna){
  //your code here
  let result = ''
  for(i=0;i<dna.length;i++) {
    if(dna[i] === 'A'){
      result+= 'T'
    }
    else if (dna[i] === 'T'){
      result+='A'
    }
    else if (dna[i] === 'G') {
      result+= 'C'
    }
    else if (dna[i] === 'C') {
      result += 'G'
    }
  }
  return result
}
```
