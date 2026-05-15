# Quiz-App
Stores questions + answers, track score, show results at end. 


## Full Program

quiz = [
    {"q": "Capital of France?", "opts": ["London", "Paris", "Berlin", "Madrid"], "a": "Paris"},
    {"q": "Red Planet?", "opts": ["Venus", "Jupiter", "Mars", "Saturn"], "a": "Mars"},
    {"q": "5 + 7?", "opts": ["10", "11", "12", "13"], "a": "12"},
    {"q": "Who wrote Romeo and Juliet?", "opts": ["Dickens", "Shakespeare", "Austen", "Twain"], "a": "Shakespeare"},
    {"q": "Largest ocean?", "opts": ["Atlantic", "Indian", "Arctic", "Pacific"], "a": "Pacific"},
    {"q": "Chemical symbol for water?", "opts": ["H2O", "CO2", "O2", "NaCl"], "a": "H2O"},
    {"q": "How many continents?", "opts": ["5", "6", "7", "8"], "a": "7"},
    {"q": "Python named after?", "opts": ["Snake", "Monty Python", "Game", "Mathematician"], "a": "Monty Python"},
    {"q": "WWII end year?", "opts": ["1943", "1944", "1945", "1946"], "a": "1945"},
    {"q": "Square root of 64?", "opts": ["6", "7", "8", "9"], "a": "8"},
]

# print(quiz[0]['q'],quiz[0]['opts'],quiz[0]['a'])
seen=set()
score=0
pass_score=5
print('questions')
i=1
for question in quiz:
    print(f'{i} {question['q']}')
    i+=1
while True:
    q_no=input('choose a question no:')
    if q_no=='quit':
        break
    q_no=int(q_no)
    if q_no>10 or q_no<1:
        print('invalid no')
    elif q_no in seen:
        print('question already solved')
    else:
        print(quiz[q_no-1]['q'])
        print('options:',(quiz[q_no-1]['opts']))
        ans=input('enter correct answer:').lower()
        if ans==quiz[q_no-1]['a']:
            print('correct answer!')
            score+=1
        else:
            print('wrong answer!')
        seen.add(q_no)
print('attempted question:',len(seen))    
print('Final score :',score)
if score>=pass_score:
    print('you passed the quiz')
else:
    print('you failed the quiz')

    




    
    
