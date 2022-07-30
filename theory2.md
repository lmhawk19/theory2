<h2>1. How does Object Oriented Programming differ from Process Oriented Programming?</h2>

<p>Object Oriented Programming (OOP) is a programming paradigm that provides a way to structure programs 
where properties and behaviours are bundled into individual objects. It is a way to create real-world things, 
like a cat or a vehicle as well as the relationships between things like between universities and students or employees and employers. 
For example, an <b>object</b> could be an ebook, with <b>properties</b> like title, length, author and <b>behaviours</b> like open, close, read, bookmark 
and/or highlight. It is best used for large and complex programs. In OOP the data is more important than the function, 
you can reuse code and overloading can occur. It is quite easy to add new data and functions. 

Object Oriented Programming languages include C, C++, Java, Go, Ruby and Python. 

Alternatively, Process Oriented Programming structures a programme more like a recipe, 
with a set of instructions (functions and code blocks) to follow in order to complete an assignment. 
It is best used for medium-sized programs. The function is more important than the data in Process Oriented Programming. 
You cannot reuse code, nor can you use data hiding or inheritance and overloading is impossible. Unlike with OOP, 
it is very difficult to add new data and functions. 

Process Oriented Programming languages include C, FORTRAN, Pascal and Basic.</p>

<h2>2. What's polymorphism in OOP?</h2>

<p>Polymorphism is where data can be processed in several different forms and is a key concept of OOP. 
Poly means many and morphism means types. For example a man can be a father, a son and a brother - 
he is different things for different people. A common use of polymorphism in OOP is where a parent class 
references a child class object. Polymorphism is a property through which any message can be sent to 
objects of multiple classes. Languages that don’t support polymorphism cannot call themselves OOP languages, 
they must call themselves object-based languages. </p>

<h2>3. What's inheritance in OOP?</h2>

<p>Inheritance in OOP is where you create a hierarchy of classes where one class derives from another a set 
of attributes and methods. The sub or child class will inherit from the super or parent class. 

In the example below we can see that the parent class is vehicle, with the child classes car and boat, 
inheriting attributes and methods from their parent. This being said, in adding attributes to child classes, 
we don’t change the parent attributes. Eg. Boat can move, make noise and have an age just like car can but 
it can’t reverse because only car can do that. 

</p>

~~~
from datetime import datetime


class Vehicle:

    def __init__(self, make, year, colour, noise):
        self.make = make
        self.year = year
        self.colour = colour
        self.noise = noise

    def move(self, distance):
        print(f"The {self.make} travelled {distance}m.")

    def make_noise(self):
        print(f"The {self.make} goes {self.noise}!")

    def get_age(self):
        age = datetime.today().year - self.year
        print(f"The {self.make} is {age} years old.")


class Car(Vehicle):

    def __init__(self, make, year, colour):
        super().__init__(make, year, colour, "beep")

    def reverse(self, distance):
        print(f"The {self.make} reversed {distance}m.")


class Boat(Vehicle):
    def __init__(self, make, year, colour):
        super().__init__(make, year, colour, "swoosh")

    def run_aground(self):
        print(f"The {self.make} ran aground.")


my_car = Car("Mazda", 2011, "blue")
your_car = Car("Hyundai", 2016, "blue")
my_boat = Boat("Boaty McBoatface", 2018, "white")

my_car.move(10)
your_car.move(20)
my_car.make_noise()
your_car.make_noise()
my_car.get_age()
your_car.get_age()
my_boat.make_noise()
my_car.reverse(123)
my_boat.move(100)
my_boat.run_aground()
~~~

<h2>4. If you had to make a program that could vote for the top three funniest people in the office, how would you do that? How would you make it possible to vote on those people?</h2>

<p>
First I would make employees ‘register’ to vote or register them myself. I also need a list of contenders. In the example below, only 5 people want to vote. 
</p>

~~~

# To register person name who want to participate in vote
person = []
for i in range(1, 6):
    person_name = input("Enter your name :")
    person.append(person_name)
    n = len(person)
    if n < 5 :
        print("You have been successfully registered")
    else :
        print("Maximum candidates have been enrolled")

# To register candidates who want to cast their vote   
voter = []
number = int(input("Enter total number of voters want to cast their vote :"))
for i in range(1,number + 1):
    voter_id = int(input("Enter voter id number :"))
    voter.append(voter_id)

#Create a loop to see if the voter list is empty and if votes have been cast, to calculate the result. 

while True :
    if voter ==[]:
        print("Voting is over.")
        max = person_1_votes
        if person_2_votes > max:
            max = person_2_votes
            percent = (person_2_votes/num_of_voter)*100
            print(person[1],"has won","with",percent,"% votes")
            break
        elif person_3_votes > max:
            max = person_3_votes
            percent = (person_3_votes/num_of_voter)*100
            print(person[2],"has won","with",percent,"% votes")
            break
        elif person_4_votes > max:
            max = person_4_votes
            percent = (person_4_votes/num_of_voter)*100
            print(person[3],"has won","with",percent,"% votes")
            break
        elif person_5_votes > max:
            max = person_5_votes
            percent = (person_5_votes/num_of_voter)*100
            print(person[4],"has won","with",percent,"% votes")
            break
        else :
            percent = (person_1_votes/num_of_voter)*100
            print(person[0],"has won","with",percent,"% votes")
            break
         
         
    else :    
         voter_id = int(input("Enter your voter-id no :"))
         if voter_id in voter:
            print("You are a voter ")
            voter.remove(voter_id)
      
            print("Here are our contenders:")
            print(" 1.person-1 : ",person[0],
                  "\n 2.person-2 :",person[1],
                  "\n 3.person-3 :",person[2], 
                  "\n 4.person-4 :",person[3],
                  "\n 5.lperson-5 :",person[4])
             
            vote = int(input("Cast your vote for person 1 or person 2 or person 3 or person 4 or person 5  :\n"
             " Write only the no of person (like 1 or 2 ) :\n"))
            if vote == 1:
               person_1_votes+=1
               print("Thank you for casting your vote.")
            elif vote == 2:
               person_2_votes+=1
               print("Thank you for casting your vote.")
            elif vote == 3:
              person_3_votes+=1
               print("Thank you for casting your vote.")
            elif vote == 4:
              person_4_votes+=1
               print("Thank you for casting your vote.")
            elif vote == 5:
               person_5_votes+=1
               print("Thank you for casting your vote.")
            else :
                print("Person is not found. \n Please enter correct person number.")         
         
         else :
                
               print("You have already voted or have input an invalid voter id.  ")

~~~

<h2>5. What's the software development cycle?</h2>

<p>The software development life cycle, or SDLC, is a method of delivering software to the client in a series of steps. As its name suggests, SDLCs are cyclical and ongoing. Version 1 of a piece of software is almost never the ultimate, final incarnation of that piece of work. New features and fixes, maintenance and modification continue long after the first iteration of a piece of software. 
There are several different types of SDLCs. There are always steps that dictate design, deployment and maintenance but how these are ordered and conducted vary greatly from life cycle to life cycle. 
For example, in an agile SDLC there are 7 steps that are conducted one after the other, in a loop. So after you have completed step seven, you then continue with step 1 and so on. They commonly occur in the below order, though they can also be mixed together. The first 2 steps, Plan and Requirements, exist in the problem space. Everything from the Design step onwards exists in the solution space. 

<b>Plan</b> (resources, capacity, scheduling, cost, provision) We do something called a work breakdown structure and alot capacity. Teams do up a gantt chart. A critical path is made up. A cost estimate is done. 

<b>Requirements</b> (aims, project needs, business needs, eg. ‘It needs to execute in 1 second.’) You should always put together a requirements spreadsheet with a statement in the format ‘the platform should be able to …. Show my calendar, require a username and password to enter etc.’ This is called a requirements gathering phase. We list them all out and put them in a spreadsheet. At the end of this you should have an idea of what you are going to build. 

<b>Design</b> (backend, user interfaces, integration between backend and frontend, eg. architecture diagrams) You are now in the solution space. It is here you design how it is going to work and how the multiple parts will fit together.

<b>Implementation</b> (Actually building it!) Speed is key in this step. Depending on the methodology, this phase may be conducted in time-boxed “sprints,” (Agile) or may proceed as a single block of effort (Waterfall.) 

<b>Test and integrate</b> (unit tests, end to end tests, security and penetration testing where you actually try to break your app, so many types of tests. This is done in a staging environment.)

<b>Deploy</b> (deploy it to its actual production environment, so the users can actually access it)

<b>Maintain</b> (bug reports, feature requests, scope additions)

This cycle keeps repeating. It is circular. After maintenance you go back to the planning stage to plan the scope addition, bug elimination etc. 

</p>

<h2>6. What's the difference between agile and waterfall?</h2>

<p><b>Agile</b> is both a SDLC and a set of values and principles; a collection of beliefs that teams can use for making decisions about how to do the work of developing software. 

The stages vary slightly in name but consist of:
<ol><li>Plan</li>
<li>Requirements</li>
<li>Design</li>
<li>Implementation</li>
<li>Test and integrate</li>
<li>Deploy</li>
<li>Maintain</li>
</ol>

Agile values: 
<ul><li>Customer collaboration over contract negotiation.</li>
<li>Individuals and interactions over processes and tools. </li>
<li>Working software over comprehensive documentation. </li>
<li>Responding to change over following a plan. </li>
</ul>

Principles:
<ul><li>The developers should be working with the business people daily; a collaborative approach. </li>
<li>Highest priority is to deliver software to the client. </li>
<li>Welcoming changing requirements, even late in the game. </li>
<li>Deliver software frequently, and within the shortest timescale possible. </li>
<li>Build projects around motivated individuals and trust that they will get the job done; no micromanaging in agile environments. </li>
<li>Working software is the primary measure of progress. </li>
<li>Sustainable development - teams should be supported to maintain a constant pace.</li>
<li>Simplicity. Work smarter not harder. </li>
<li>Self-organizing teams.</li>
<li>Reflection and adjusting behaviour accordingly. Learning from what has been done previously.</li>
</ul>
<b>Waterfall</b> is the earliest SDLC model and is both linear and sequential. It has 6 stages that cascade downwards. One stage must be completed before another begins. The development process looks flowing, moving step by step. 

The stages vary slightly in name but consist of:
<ol><li>Requirement Gathering Stage/Feasibility Study</li>
<li>Design Stage</li>
<li>Built Stage/Implementation</li>
<li>Integration and Test Stage</li>
<li>Deployment Stage</li>
<li>Maintenance Stage</li>
</ol>

This SDLC model values:
<li>Gradual execution of every stage completely</li>
<li>Strict and elaborate documentation</li>
<li>No overlap between stages</li>
<li>Minimal client interaction</li>
<li>QA testing completed after each stage</li>
<li>Clear, pre-defined requirements</li>
</ul>


</p>

<h2>7. What is a reduced function used for?</h2>

<p>In python 3, reduce is no longer a builtin function and has been demoted to a functool. It can be replaced by a for loop. 
If you have a sequence of data and a function that takes two arguments, it will apply the first to the first two terms, it will then take the result of this and apply it to the third piece of data, then repeat the process until it has worked its way through the entire list. Then it will return the final value. 

First you have to import the reduce function from the functools module then input a function that takes two inputs. In the below example, we multiply all numbers in a list:
</p>

~~~
from functools import reduce
#Multiply all numbers in a list

data = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]
multiplier = lambda x, y: x * y
reduce(multiplier, data)

Returns: 6469693230

~~~

<h2>8. How does merge sort work?</h2>

<p>Merge sort is a divide and conquer algorithm insofar as it breaks down the initial problem into subproblems recursively until they are small enough to be easy to solve. The solutions are then combined to solve the initial problem. 

For example, if we want to sort an array using merge sort. We would split the array in half recursively, merge sort on each half and then merge the two sorted halves back into one, sorted array. 

For example:
</p>

~~~

def mergeSort(myList):
    if len(myList) > 1:
        mid = len(myList) // 2
        left = myList[:mid]
        right = myList[mid:]

        # Recursive call on each half
        mergeSort(left)
        mergeSort(right)

        # Two iterators for traversing the two halves
        i = 0
        j = 0
        
        # Iterator for the main list
        k = 0
        
        while i < len(left) and j < len(right):
            if left[i] <= right[j]:
              # The value from the left half has been used
              myList[k] = left[i]
              # Move the iterator forward
              i += 1
            else:
                myList[k] = right[j]
                j += 1
            # Move to the next slot
            k += 1

        # For all the remaining values
        while i < len(left):
            myList[k] = left[i]
            i += 1
            k += 1

        while j < len(right):
            myList[k]=right[j]
j += 1
            k += 1

myList = [54,26,93,17,77,31,44,55,20]
mergeSort(myList)
print(myList)

Prints: [17, 20, 26, 31, 44, 54, 55, 77, 93]

~~~

<h2>9. Generators - Generator functions allow you to declare a function that behaves like an iterator, i.e. it can be used in a for loop. What is the use case?</h2>

<p>Python generators are a simple way of creating iterators. 
A generator is a function that returns an object (iterator) which we can iterate over (one value at a time). These functions do not produce all the items at once - they produce them one at a time and only when required. Whenever the for statement is included to iterate over a set of items, a generator function is run. In python, we need generators to easily produce iterables, especially in large volumes. Generators can be used to produce an infinite number of items and pipeline a number of operations. 
<br>
With a generator, instead of using a return keyword we use a yield keyword to get the output. 
You would use generators with a for loop if you want to execute the same function at once. The loop would iterate over the objects and when it is complete, will stop. 
<br>For example:
</p>

~~~
def z():
    n=1
    yield n
    n=n+3
    yield n
for x in z():
    print(x)

Outputs: 
1
4

~~~

<h2>10. Decorators - A page for useful (or potentially abusive?) decorator ideas. What is the return type of the decorator?</h2>

<p>The original object, the one which is going to be modified, is passed to a decorator as an argument. The decorator returns a modified object, e.g. a modified function, which is bound to the name used in the definition.
Decorators will return that modified object. 

Syntax:
def decorator_function(function):

def inner_wrapper_function()
	# some logic
	function()
 	# some logic

return inner_wrapper_function

<br>
For example:

</p>

~~~
def add_one(num):
    return num + 1

Def operate(func, value):
Return func(value)

print(operate(add_one, 4))

#Returns: 5

#Example 2: 
#The below function can only pass if my name is used to run it.

def only_allow_if_name_match(func):
    def guarded_function(*arg):
        name = input("Please enter your first name")
        if name == "Lucy":
            func(*arg)
        else:
            print("Sorry, no entry")
    return guarded_function

@only_allow_if_name_match
def first_greeting():
    print("Welcome Lucy")
~~~

