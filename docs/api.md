# Quiz Game Library API

### Initialize a quiz object

| Property   | Type|Description |
|------------|-----|------------|
| question| String | the question set by developer|
|answer| Array| the array of answers including text of question and the correction|
| text| Sting| text of the answer|
| correct|Boolean  | set the answer to be correct or not|
| item| Array of Arrays | you can set each item with question and answer|

You can set item in the fomat of below

```
item: {
        question: "What is 1+1 ?",
        answers: [
            { text: '1', correct: false },{ text: '2', correct: true },...]
    }
```
You can initialize quiz game object in the fomat below
```
{
    {
        question: "...",
        answers: [{ text: '...', correct: false },{ text: '...', correct: true },...]
    },
    {
        question: "...",
        answers: [{ text: '...', correct: true },...]
    },
        ...
    }
```

### Events
When user click on the "Start" , "Next",and "Restart Quiz" it reset the status of the quiz object by resetStatus() to hide the "Next". Only after click on "Answers", "Next" will appear


|Event |Discription|
|-----|----|
|`startButton.addEventListener('click', startQuiz)`| add event listener if the startbutton is clicked, run the function startQuiz()   |
|`nextButton.addEventListener('click',()=>{goToNextQuestion()})`| if the next button is clicked display the next question  |
|`button.addEventListener('click', selectAnswer)`| add event listener is the answer button is clicked run the seleceAnswer() function to count the score from selectAnswer   |
|`selectAnswer(event)`| take in a event as a parameter, get the button answer that user selected and records the correct and wrong answer, set correct answer to button dataset  |




### Methods

|Name       |Params     | Discription   |
|-----------|-----------|---------------|
|startQuiz()           |       N/A    |    start the quiz start the timmer inside          |
|randomOrder(questions)     |questions Object with Array of Arrays inside      |     shuffuled through the questions to generate random order of the questions everytime when start the quiz      |               |
|   goToNextQuestion()        |   N/A         |     Move to next question and display |
| displayQuestion(question)          |       question    |    populating different answers in the question           |
|startSetTime()           |    N/A        |   Set timmer for quiz modify `let timmer = 10;` and `(timmer > -1) {startSetTimeDate = setTimeout(() => {fun();}, 1000);` to change the timmer period          |
|resetState()           |     N/A       |  clear out old answer for the previous question when move to next function           |
|createAnswerButton(question)           |   question        |    create the answear button pass in the answear set in question           |
|checkIfhaveNext(mark)           |      mark     |    check if the question have next question behind, if not, the next button will not display          |
| setStatus(element, correct)          |  element, correct         |    clear the status of correct and wrong after finish answer each question so that the correct and wrong answers can be updated in next question        |
|  clearStatus(element)         |   element        |  clear correct and wrong status for answer button             |
| getResult(length)          |  length         |    get the result for the quiz when finish all question and didn't restart the quiz          |



### Callbacks
|Property |Type|Description|
|---------|-----|-----------|
|`forEach`|  function |  Iterarate through the answer button to set the status of answer button |