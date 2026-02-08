<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name: THEJASHREE S</h3>
<h3>Register Number: 212224240175 </h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

## program:
```python
import random
import string
def mutate_solution(soln):
    ind=random.randint(0,len(soln)-1)
    soln[ind]=random.choice(string.printable)
    return soln

def generate_random_solution(answer):
    l=len(answer)
    soln=[random.choice(string.printable) for _ in range(l)]
    return soln

def evaluate(answer,best_soln):
    s=list(answer)
    t=best_soln
    diff=0
    for i in range(len(s)):
        diff+=abs(ord(s[i])-ord(t[i]))
    return diff

def SimpleHillClimbing():
    answer=input()
    best_soln=generate_random_solution(answer)
    best_score=evaluate(answer,best_soln)
    
    while True:
        print("Score:{}String:{}".format(best_score,"".join(best_soln)))
        if best_score==0:
            #print("Score:{}String:{}".format(best_score,"".join(best_soln)))
            break
        else:
            new_solution=mutate_solution(list(best_soln))
            score=evaluate(answer,new_solution)
            if score<best_score:
                best_score=score
                best_soln=new_solution
                
SimpleHillClimbing()
```
<hr>
<h2>Sample Input and Output</h2>
<h2>Sample String:</h2> Artificial Intelligence
<h2>Output:</h2>
Score: 643  Solution :  8RzF:oG ]%;CPORRMe!zGvk<br>
Score: 609  Solution :  8RzF:oG ]%;CPqRRMe!zGvk<br>
Score: 604  Solution :  8RzF:oG ]%;CPqRRMe!zGqk<br>
Score: 594  Solution :  8RzF:oG ]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
....................................................<br>
..................................................<br>
................................................<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 0  Solution :  Artificial Intelligence<br>

## Input and Output
<img width="355" height="884" alt="image" src="https://github.com/user-attachments/assets/d6262439-1e25-4128-bc43-045a5ba591cf" />
<img width="304" height="879" alt="image" src="https://github.com/user-attachments/assets/bec1bd15-5c11-483f-bd61-a2ec7547f588" />
<img width="215" height="750" alt="image" src="https://github.com/user-attachments/assets/95a09867-f571-4168-bad8-2b0193ac32ae" />


## Result:
