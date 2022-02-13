# Entry 3
##### 2/13/22

## Content

At this point, I should be prepared to begin planning my project. In terms of the websites I've been utilizing, I've been using IDE CS50 to test my Firebase tool. Later in this blog, I'll demonstrate snippets of my code. It is recommended, but not required, to utilize my IDE as (example or testing)[ide.cs50.io] for deeper understanding.

Firebase is the tool that I've been focused on, and I'll continue to obtain it. I've been using its FireStore feature in general. This is most likely the tool's most important feature for storing and retrieving data. Furthermore, my current project is a countdown with specific events that you want to assign. It's efficient because it allows quick user input that is placed directly into a list and saved in the database with their userID and username information, where I'll discuss shortly in the blog.

When it comes to skills, when tinkering with my tool, I've learnt to acknowledge error and troubleshooting. When I first tried to implement Firebase into my Web App, I encountered several issues. I noticed I had installed an older version of the database just by browsing at the code, despite the fact that I was somewhat new to the program. I just transferred from a Realtime-Database to the new Cloud Firestore to troubleshoot this.

``<script src="https://www.gstatic.com/firebasejs/8.1.1/firebase-app.js"></script>``

``<script src="https://www.gstatic.com/firebasejs/8.1.1/firebase-firestore.js"></script>``

It allows the Firebase App to send the tools virtually as if it were importing them into the html file, as shown by the first code. The next algorithm is very similar to the first, but it downloads a different collection of libraries, the Fire Store, which is a form of database run by Firebase. In a short, the first line is required for everything to operate, while the second line accesses the database to allow the data from the html to be analyzed.


While returning to Firebase, I was able to gain a better understanding of the tool and develop something straightforward but useful. In terms of my references, I went over the firebase documentation once more, but this time I aimed on how to add data and retrieve data. Afterwards, I'll demonstrate parts of my mini-project that I was working on while experimenting with Firebase. My IDE will be used to reference all of the code shown.

Here are some snippits of code that I have in my project so far:

```javascript
    var userDoc = usersRef.doc("user")
    var eventName = prompt("What's your event name?")
    var userName = prompt("What's your name?")

       if (eventName != null && userName != null){
        userDoc.set({
        name:  userName,
        event: eventName
    },
    {merge: true} 
    )}
```
The simple if statement in the code above simply means that the information has been entered prior to saving it. Another new thing I learned from Firebase is in the code INSIDE the if statement. It initially connects to the document, then saves data with the area and value associated with it. Before this case, I've set the name field to userName, which is the variable I created previously. This saves the code to Firestore, from which it can be used later.

```javascript
    userDoc.get().then((doc) => {
        var event = doc.data().event
        document.write("Event Name: " + event)
    })
```

Inside the code above, it's a set of instruction that basically allows the data to be taken from the Firestore Database and printed into the html element of the webpage. It seemed a little confusing at first, but it is just waiting for the Cloud Firebase document to be referred back to the code, after which the script can change the data inside it. I've just used document in this example. write to insert the "Event" as well as its linked value in to the DOM.
## EDP
I would say that I am in stage 3 and 4 of Engineering since I have an idea on how to save user data using JS to save in a Firebase database. Although I haven't completed a framework, I have constructed something that could be useful in my Freedom Project. I'd say I've thought about how I'm going to construct my webpage, but I haven't decided how I'm going to do it. Based on what I've done so far, I've constructed a small webpage that asks the user for their name and the assignment they need to complete. I may then save and access their information. Because I haven't yet established a thorough framework for this Countdown Event App. The next stage in the Engineering Design Process will be to build a completely functional web application that collects and stores user input into the webpage.
## Skills
Eventually, the Freedom Project has taught me some new skills. I've learned about Time Management and Organization in specific. These two abilities are extremely beneficial and necessary. I've improved my time management skills. I learned not to push stuff into my head while working on my project. Browsing at the documentation or tutorial, then taking a pause before returning to it, is what works best for me. This is especially beneficial to me because it is more practical than wasting time attempting to understand something that my mind cannot process. To help me organize things much better, I've been using comments as annotations, which has helped me organize it significantly better than previously.


[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)