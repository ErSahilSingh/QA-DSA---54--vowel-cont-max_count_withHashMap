# QA-DSA---54--vowel-cont-max_count_withHashMap

/**
 * @param {string} s
 * @return {number}
 */
var maxFreqSum = function(s) {
    //if any things that need to find out count or search than use hash map
    let map= {}

    //loop and add into has map
    for(let i=0;i<s.length;i++){
        if(!map[s[i]]){
            map[s[i]]=1
        }else{
            ++map[s[i]]
        }
    }

    //campare and get max vowel and cont
    let vowelList=['a','e','i','o','u']
    let maxVowel=0;
    let maxConsonent=0;
    for(let i=0;i<s.length;i++){
       if(vowelList.includes(s[i])){
            if(map[s[i]]>maxVowel){
                maxVowel=map[s[i]]
            }
       }else{
            if(map[s[i]]>maxConsonent){
                maxConsonent=map[s[i]]
            }
       }
    }

    return maxVowel+maxConsonent
    
};
