const crypto = require('crypto') ,
hash = crypto.getHashes();

let currentPassword = [];

function supplyPassword() {
    let passwords = ['password', 'pass', 'supersecret'];
    for (let i = 0; i < passwords.length; i++) {
        currentPassword.push(passwords[i]);
    }
}

supplyPassword();

(function(knownHashes, ourGuesses) {
    let ourGuessesHashes = [];
    let matches = [];
    
for (let guesses_iteration = 0; guesses_iteration < ourGuesses.length; guesses_iteration++) {
  ourGuessesHashes.push(crypto.createHash('sha256').update(ourGuesses[guesses_iteration]).digest('hex'));
}

for (let knownHashesIteration = 0; knownHashesIteration < knownHashes.length; knownHashesIteration++) {
  for (let ourGuessesIteration = 0; ourGuessesIteration < ourGuessesHashes.length; ourGuessesIteration++) {
      
      if (knownHashes[knownHashesIteration] == ourGuessesHashes[ourGuessesIteration]) {
          matches.push(currentPassword[ourGuessesIteration], ourGuessesHashes[ourGuessesIteration]);
      }
  }
}
let result = {
    'Known Hashes': knownHashes, 
    'Password Guesses': ourGuesses,
    'Guessed Password Hashes': ourGuessesHashes,
    'Matches': matches
}

console.log(result);


})(['5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8', '3a6eb0790f39ac87c94f3856b2dd2c5d110e6811602261a9a923d3bb23adc8b7','d74ff0ee8da3b9806b18c877dbf29bbde50b5bd8e4dad7a3a725000feb82e8f1','4a2ef9e7267d9f14597da148c1994c743ab6c8e87b5d30404e13c7d4ca2057a8'], currentPassword); 

// d74ff0ee8da3b9806b18c877dbf29bbde50b5bd8e4dad7a3a725000feb82e8f1 pass

// 5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8 password
