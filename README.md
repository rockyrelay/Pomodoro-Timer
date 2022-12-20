# Georgia's Pomodoro Timer App

As per the end of the FAC 26 Skills Bootcamp, we were tasked with some project-prompts, designed to help us revise the fundamentals we have learnt during the course.

I have chosen to create a Pomodoro Timer. :tomato: 

The Pomodoro technique is a time management method developed by Francesco Cirillo in the late 1980s. I use pomodoro timers whether I'm studying code, languages, and throughout my career. Time to build one myself!

You can read about the pomodoro technique on Cirillo's site [here](https://francescocirillo.com/products/the-pomodoro-technique).

---

## Project Goals

### Features 
- [ ] A “work” timer that counts down to zero (usually 25 minutes).
- [ ] A second “break” timer that counts down to zero (usually 5 minutes).
- [ ] Buttons to start a session, pause the timer, or cancel the session and restart.

### Stretch goals 
- [ ] Customisable lengths of time for work/break.
- [ ] Save custom lengths to localStorage.
- [ ] Play an alarm sound to make it obvious the time is up.

### Learning outcomes 
- [ ] Timers in JavaScript.
- [ ] Coordinating event handlers.
- [ ] Managing ongoing state.

### Technical Requirements
- [ ] Configure dev tooling:
- [ ] Prettier formatting
- [ ] ESLint linting
- [ ] Live-reloading local dev server
- [ ] Publish code to GitHub
- [ ] Deploy app to GitHub Pages

---

## Personal Deadline

- [ ] **03/01/2023**

---

<head>
<style>
#demo {
  text-align: center;
  font-size: 2rem;
  font-family: helvetica, sans-serif;
  background-color: #475269;
  color: #fff069;
  padding: 1rem;
  max-width: 30%;
  border-radius: 0.5rem;
}
</style>
</head>
<body>

<p id="demo"></p>

<script>
// Set the date we're counting down to
let countDownDate = new Date("Jan 3, 2023 10:00:00").getTime();

// Update the count down every 1 second
let x = setInterval(function() {

  // Get today's date and time
  let now = new Date().getTime();
    
  // Find the distance between now and the count down date
  let distance = countDownDate - now;
    
  // Time calculations for days, hours, minutes and seconds
  let days = Math.floor(distance / (1000 * 60 * 60 * 24));
  let hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  let minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
  let seconds = Math.floor((distance % (1000 * 60)) / 1000);
    
  // Output the result in an element with id="demo"
  document.getElementById("demo").innerHTML = days + "d " + hours + "h "
  + minutes + "m " + seconds + "s ";
    
  // If the count down is over, write some text 
  if (distance < 0) {
    clearInterval(x);
    document.getElementById("demo").innerHTML = "Deadline passed - project __ x";
  }
}, 1000);
</script>
</body>
