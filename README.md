<p align="center">
  <a href="" rel="noopener">
 <img width=200px height=200px src="https://i.imgur.com/6wj0hh6.jpg" alt="Project logo"></a>
</p>

<h3 align="center">Exam 2050 Problems</h3>

<div align="center">

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![GitHub Issues](https://img.shields.io/github/issues/VoidChips/exam-2050-problems.svg)](https://github.com/VoidChips/exam-2050-problems/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/VoidChips/exam-2050-problems.svg)](https://github.com/VoidChips/exam-2050-problems/pulls)

</div>

---

<p align="center"> 
You have to take a test in the game, which results in different endings based on your score. <br> 
Taking place in a dystopian society, this single test determines your future. The test has problems from multiple subjects. <br>
Getting a low score means getting sent to the labor camp with horrible conditions, or worse. <br>
The class average is also factored into your grade, so you have to also perform well compared to your peers.
</p>

## 📝 Table of Contents

- [About](#about)
- [How to contribute](#how_to_contribute)
- [Authors](#authors)

## 🧐 About <a name = "about"></a>
Look up the files in this project if you want to see the answers for problems in Exam 2050.
If you want to add problems, see below.


## 🏁 How to contribute <a name = "how_to_contribute"></a>

Each exam has 50 problems.  
To add a problem, create a *problemX* directory under an exam with less than 50 problems, with X being the problem number.  
If the existing exams already have 50 problems, create a new exam directory and create the problem directory there.
Each problem directory must contain a *description.json* file with details of the problem.  

### Properties in description.json

- **exam**:  
  > The exam number. *integer*
- **number**: 
  > The problem number. *integer*
- **type**: 
  > The problem type. *string*
  + **"multiple choice"**: 
    > A multiple choice problem with one correct answer.
  + **"multiple response"**: 
    > A muliple choice problem with zero, one, or multiple answers.
  + **"free response"**: 
    > Also known as an essay question, there are no choices. However, there is a predetermined answer.
- **useImage**: 
  > Determines if the problem uses an image to ask the question instead of the string from **problem** property. *boolean*
- **problem**: 
  > The prompt for the problem. Ask your question here. If **useImage** is set to true, the value here is ignored. *string*
- **choices**: 
  > The choices for multiple choice or multiple response problems. The key is the choice and the value is the answer associated with the choice.  
  If **useImage** is set to true, this property is still required to display the choices that can be selected.  
  *key value pairs of string, integer/boolean/string*
- **answer**: 
  > The correct answer to the problem. If **type** is *"multiple response"* and there are no correct answers, use *null* or an empty array.
  + **"multiple choice"**: *string*
  + **"multiple response"**: *string[]*
  + **"free response"**: *string*


**Example**: Create problem #20 for exam 3, which is a multiple choice question.
1. Create *problem20* directory in */exams/3*
2. Create *description.json* file in */exams/3/problem20*.
3. In *description.json*, add details. The correct choice is b, so the answer is "choice 2".
```
{
    "exam": 3,
    "number": 20,
    "type": "multiple choice",
    "useImage": false,
    "problem": "Example",
    "choices": {
        "a": "choice 1",
        "b": "choice 2",
        "c": "choice 3",
        "d": "choice 4"
    },
    "answer": "b"
}
```

**Example**: *description.json* for a multiple response problem with one correct answer. The correct answer is "choice 1".
```
{
    "exam": 2,
    "number": 4,
    "type": "multiple response",
    "useImage": false,
    "problem": "Example",
    "choices": {
        "a": "choice 1",
        "b": "choice 2",
        "c": "choice 3",
        "d": "choice 4"
    },
    "answer": ["a"]
}
```

**Example**: *description.json* for a multiple response problem with multiple correct answers. The correct answers are "choice 1" and "choice 2".
```
{
    "exam": 1,
    "number": 33,
    "type": "multiple response",
    "useImage": false,
    "problem": "Example",
    "choices": {
        "a": "choice 1",
        "b": "choice 2",
        "c": "choice 3",
        "d": "choice 4"
    },
    "answer": ["a", "b"]
}
```

**Example**: *description.json* for a free response problem. The correct answer is "example".
```
{
    "exam": 3,
    "number": 25,
    "type": "free response",
    "useImage": false,
    "problem": "Example",
    "answer": "example"
}
```


## ✍️ Authors <a name = "authors"></a>

- [@kylelobo](https://github.com/kylelobo) - Idea & Initial work

See also the list of [contributors](https://github.com/VoidChips/exam-2050-problems/contributors) who participated in this project.