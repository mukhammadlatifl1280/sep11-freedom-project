# Entry 5
##### 04/25/22


At the moment, I have finally finished my MVP(Minimum Valuable Project). The minimum thing for my project was that I had to have a countdown web app where it saves the user info through firebase including the event name.

As you click the link below, it brings you to the jsbin where I inserted the full javascript code that I wrote by myself to store in the firebase. It also includes all the comments on specific lines in order to keep track what each line represents for. To make it short, the javascript includes a if statement, objects, functions, event listener(button), arrays to save in the firebase as well as strings and finally a merge function where it takes all the info and sends it to the firebase.

[Link to the code](https://jsbin.com/bebuqebeki/edit?js,output)

## **Challenges/Takeaways**

To look from my perspective, making this project was the most hardest one I have ever done and I have encountered many challenges throughout making the project. The most challenging part was getting the data from the firebase and displaying it to the HTML. For example, I wanted to save the data that was inputed by the user and store it to the firebase. Then after they refresh the page or log back in, I want all their data to display as what it looked like before. In the code below it shows where the part that actually saves the code and stores it to the firebase

```js
// assign the initialized variables with the ID
var saveButton = document.querySelector("#save");
saveButton.addEventListener("click", function(){
    inputMonths = document.querySelector("#month"); 
    inputDays = document.querySelector("#day");
    inputYears = document.querySelector("#year");
    inputHours = document.querySelector("#hour");
    inputMinutes = document.querySelector("#min");
    listEvents = document.querySelectorAll("li");
    console.log(inputMonths.value + " " + inputDays.value + " " + inputYears.value + " " + inputHours.value + " " + inputMinutes.value);
   
    var userEvent = []; // array for saving the event name
    listEvents.forEach(function(li){
        userEvent.push(li.innerHTML);
    });
    
    var listDays = document.querySelectorAll("#timer_days");
    var userCountdownDays = []; // array to save for days
    listDays.forEach(function(month){
        userCountdownDays.push(month.innerHTML);
    });
    
    var listHours = document.querySelectorAll("#timer_hours");
    var userCountdownHours = []; // array to save for hours
    listHours.forEach(function(timer_hours){
        userCountdownHours.push(timer_hours.innerHTML);
    });
    
    var listMinutes = document.querySelectorAll("#timer_minutes");
    var userCountdownMinutes = []; // array to save for minutes
    listMinutes.forEach(function(timer_minutes){
        userCountdownMinutes.push(timer_minutes.innerHTML);
    });
    
    var listSeconds = document.querySelectorAll("#timer_seconds");
    var userCountdownSeconds = []; // array to save for seconds
    listSeconds.forEach(function(timer_seconds){
        userCountdownSeconds.push(timer_seconds.innerHTML);
    });
    
    (userDocument).set({
        eventName: userEvent, // sets the user event names to the firestore
        countdownDays: inputDays.value, // sets the user inputed days to the firestore
        countdownMonths: inputMonths.value, // sets the user inputed months to the firestore
        countdownMinutes: inputMinutes.value, // sets the user inputed minutes to the firestore
        countdownHours: inputHours.value, // sets the user inputed hours to the firestore
        countdownYears: inputYears.value, // sets the user inputed years to the firestore
    }, {merge: true}); // takes all the info and sends to firestore
});
```

The code above looks very complicated to understand but it is very simple if you take time to understand. From start, I needed to save event name, the user inputted days, months, minutes, hours and minutes. Now you would wonder why would I save that inputed information and not the actual live numbers that is counting down. The main reason why I couldnt save the real live version because the value of the saved code would automatically save the code per second which means it is unnecessary to do and plus you would reach your limit to the firebase use. Then I had a idea where I would want to save the user inputed such as the one like minutes, hours, months etc. If I manage to save that information and display in the HTML then next step would be that whenever the page is loaded, it will click the button that says "Create countdown" and whenever that button is clicked by the computer itself, it will display the live countdown on the HTML.

```js
var loadPage = setInterval(() => { // whenever page loads, it will click run the saved countdown
    countdownFunction(); // run the countdown 
    clearInterval(loadPage);
}, 500); // per 500 second
```

The code above shows the part where whenever the page loads, it will run the ```countdownFunction``` per 500 second

Then as we suppose we want to save the information in the firestore, I need to have function where I would want to use ```forEach``` with array that would save the value that was inputed by the user. Then use that array to push it to the HTML with the function ```.push```. Lastly, I would need to get all that information and save it using the ```userDocument``` to set all the info in the firestore, in order to do that I would need to use ```{merge: true}``` which basically does is set with merge will update fields in the document or create it if it doesn't exists.

My main takeaway from this project of MVP was that there were many different ways to solve this problem and we all should go to the one that is simplest way because at the end you would regret that you do it the hardest way and still get the same result. Specifically to the firebase, my first thought was to save the actual data was in the live HTML but then my thought shifted to more simpler way which was to save just the inputted info by user and let the computer click the button for them whenever the page loads and it will automatically displays the countdown.


## [**EDP**](https://hstatsep.github.io/students/#edp)
I would say that I am in stage 7 and 8 of [Engineering Design Process](https://docs.google.com/document/d/1anCzhzfZUNXD713Z1PqBDSAO_tU2PbZUpvT6zi3Y0jQ/preview) since I have done all the minimum valuable project and test out all the functions. There are many things to improve in my project such as the design of the website where how it would look on the mobile devices as well as other screen sizes. Also with description of my website where I add all the useful things on what things will be stored and gathered from user. Lastly, I am at the part where I will communicate the result because everything is done and I would need to explain and see what people would think of it.

## [**Skills**](https://docs.google.com/document/d/1anCzhzfZUNXD713Z1PqBDSAO_tU2PbZUpvT6zi3Y0jQ/preview#heading=h.uuy2vesiayoa)

This Freedom Project finally led to the development of various new abilities in me. In particular, I've learned a lot about personal organization management. These two abilities are extremely beneficial and necessary. My personal management skills have improved. While working on my task, I learned not to let anything to enter my head. I find that browsing the material or instructions first, then taking a break before returning to it, works best for me. This is quite beneficial to me since it is more reasonable than wasting energy trying to comprehend something that my mind cannot fathom. I've started using comments as notes to help me organize things a lot better than before, and it's helped me a lot.

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)