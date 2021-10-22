# Q.
Description:
Polycarpus works as a DJ in the best Berland nightclub, and he often uses dubstep music in his performance. Recently, he has decided to take a couple of old songs and make dubstep remixes from them.

Let's assume that a song consists of some number of words (that don't contain WUB). To make the dubstep remix of this song, Polycarpus inserts a certain number of words "WUB" before the first word of the song (the number may be zero), after the last word (the number may be zero), and between words (at least one between any pair of neighbouring words), and then the boy glues together all the words, including "WUB", in one string and plays the song at the club.

For example, a song with words "I AM X" can transform into a dubstep remix as "WUBWUBIWUBAMWUBWUBX" and cannot transform into "WUBWUBIAMWUBX".

Recently, Jonny has heard Polycarpus's new dubstep track, but since he isn't into modern music, he decided to find out what was the initial song that Polycarpus remixed. Help Jonny restore the original song.

Input
The input consists of a single non-empty string, consisting only of uppercase English letters, the string's length doesn't exceed 200 characters

Output
Return the words of the initial song that Polycarpus used to make a dubsteb remix. Separate the words with a space.

Examples
songDecoder("WUBWEWUBAREWUBWUBTHEWUBCHAMPIONSWUBMYWUBFRIENDWUB")
  // =>  WE ARE THE CHAMPIONS MY FRIEND
# A)
```js

function songDecoder(song){
  // ...
  if(song.slice(0,3) === 'WUB') {
    song = song.slice(3);
  }
  if(song.slice(-3) === 'WUB') {
    song = song.slice(0,-3);
  }
  song = song.replace(/(WUB)/g,' ');
  // 여기서부터 공백처리 때문에 막힘  -> /(WUB)+/ 로 바꾸면 해결된다
  let res = '';
  for (let i = 0; i <song.length ; i++) {
    if(song[i] === ' ' && song[i-1] === ' ') {
      continue
  }
  else {
    res += song[i] 
  }
  }
  if(res.slice(-1) === ' ') res = res.slice(0,-1)
  if(res.slice(0,1) === ' ') res = res.slice(1)
 return res
}
```

# 새로 배운 것

```js
s ="AWUBWUBWUBBWUBWUBWUBC".split('WUB')
(7) ["A", "", "", "B", "", "", "C"]
s.filter(Boolean)
(3) ["A", "B", "C"]
```
이처럼 배열을 만들다보면 공백이 나오는데 이 공백을 처리하는게 생각보다 어려웠었다. 
그런데 필터불리언으로 가볍게 해결되는 거였다니.. 여태 문제 풀면서 ""없애려고 포문 돌렸었는데.. 뭐한건지 싶다. 문제를 많이 풀어봐야 얻어가는게 많은 것 같다.
