
from IPython.display import HTML

html_content = """
<!DOCTYPE html>
<html>
<head>
<title>Valentine Quiz App</title>

<style>
body {
    text-align: center;
    background-color: #ffe6f2;
    font-family: Arial;
}

h1 {
    color:green;
}

button {
    margin: 5px;
    padding: 10px;
    font-size: 16px;
    border-radius: 10px;
    background-color:palevioletred;
}

img {
    border-radius: 15px;
    margin: 10px;
}

#hearts {
    font-size: 30px;
    color: green;
}
</style>

</head>

<body>

<h1>💖 Valentine's Day Quiz 💖</h1>

<!-- Background Music -->
<audio autoplay loop>
  <source src="images/music.mp3" type="audio/mpeg">
</audio>

<!-- HEART ANIMATION -->
<p id="hearts">💗 💗 💗 💗 💗</p>

<!-- IMAGE AREA -->
<img id="qimage" width="0" height="0">

<p id="question"></p>

<button onclick="checkAnswer(0)" id="btn0"></button>
<button onclick="checkAnswer(1)" id="btn1"></button>
<button onclick="checkAnswer(2)" id="btn2"></button>
<button onclick="checkAnswer(3)" id="btn3"></button>

<p id="result"></p>

<p id="score"></p>

<button onclick="nextQuestion()">Next Question</button>

<script>
var questions = [

{
   q: "where did our first meeting?",
   options: ["school","park(g)","bus","i don't see you"],
   answer:1
},

{
   q: "do you still remember our first water?",
   options: ["jun22","jan22","sep22","aug22"],
   answer:3
},

{
   q: "are you comfortable with me in anytime and even everytime",
   options: ["house","hill","park","every place","ride"],
   answer:3
},

{
   q: "Do you wish to still be my Valentine??",
   options: ["no","yes","never","hate you"],
   answer:1
},

{
   q: "What's your dream?",
   options: ["i want to become a player","work","wife","all of the above"],
   answer:3
},

{
   q: "will do u beat me?",
   options: ["yes","no","never i do that","i will never do that"],
   answer: 3
},

{
   q: "do u wanna meet me?",
   options: ["no","i will come","i will try","maybe"],
   answer: 1
},

{
   q: "Where does she wish to go?",
   options: ["wonderla","manapad","long ride","all of the above"],
   answer: 3
},

{
   q: "who is mine?",
   options: ["i don't know","who","not me","its always mee"],
   answer: 3
},

{
   q: "do u luv me even if i will hate you?",
   options: ["yes","always","you are the one","all of the above"],
   answer: 3
}

];

var current = 0;
var score = 0;

function loadQuestion() {

    document.getElementById("question").innerHTML = questions[current].q;

    document.getElementById("qimage").src = questions[current].image;

    document.getElementById("btn0").innerHTML = questions[current].options[0];
    document.getElementById("btn1").innerHTML = questions[current].options[1];
    document.getElementById("btn2").innerHTML = questions[current].options[2];
    document.getElementById("btn3").innerHTML = questions[current].options[3];

    document.getElementById("result").innerHTML = "";
}

function checkAnswer(option) {

    if(option == questions[current].answer) {
        document.getElementById("result").innerHTML = "Correct Answer! 💕";
        score = score + 1;
    }
    else {
        document.getElementById("result").innerHTML = "Wrong Answer 😢";
    }

    document.getElementById("score").innerHTML = "Score: " + score;
}

function nextQuestion() {

    current = current + 1;

    if(current < questions.length) {
        loadQuestion();
    }
    else {
        document.getElementById("question").innerHTML = "Quiz Finished!";
        document.getElementById("result").innerHTML =
        "Final Score: " + score + "<br><br> 💖 You Are My Valentine Forever! 💖";

        document.getElementById("qimage").style.display = "none";
    }
}

loadQuestion();
</script>

</body>
</html>
"""
