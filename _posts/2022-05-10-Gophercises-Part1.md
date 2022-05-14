---
title: Gophercises Part 1 - Quiz Game
layout: post
author: Rachel Wang
---

### Gophercises Exercise 1 🏋🏻‍♀️ 🎉

Recently I've been exercising my Golang skills with Jon's video series [Gophercises](https://gophercises.com/). After working on the first part of exercise 1, I've learned a lot about building a client that takes user input and testing. Testing is not a requirement in any of the exercises but for the sake of best practice and TDD I added tests to my solution. One thing that really stumped me was testing user input from standard input in the console. I scoured the web and stackoverflow for answers but, was not satisfied until I found this blog post [here](https://petersouter.xyz/testing-and-mocking-stdin-in-golang/). I reframed the examples brought up in the post, into my own code for the quiz game and it turned out like the following:

<br>

```

func StartQuiz(stdin io.Reader) bool {

	var userInput string
	fmt.Println("Do you want to start the quiz? Type Y or N.")

	str, err := ReadInput(stdin)
	if err != nil {
		log.Fatal()
	}
	userInput = string(str)

	if strings.Contains(strings.ToUpper(userInput), "Y") {
		return true
	} else {
		return false
	}
}
```

<br>
StartQuiz is a function that prompts the user to start the quiz or not based on console input `y or n`. In my `TestStartQuiz` function I mocked the user input by writing strings to Golang's buffer using the bytes package. This mocks user input, as if someone is typing the commands into the terminal. As a result when I run `go test`, the test assertions I wrote with the testify package resulted in pass. 
<br>


```
func TestStartQuiz(t *testing.T) {

	var stdin bytes.Buffer
	stdin.Write([]byte("Y\n"))
	result := StartQuiz(&stdin)
	assert.Equal(t, true, result)

	stdin.Write([]byte("N\n"))
	result = StartQuiz(&stdin)
	assert.NotEqual(t, true, result)

	stdin.Write([]byte("hello\n"))
	result = StartQuiz(&stdin)
	assert.Equal(t, false, result)
}

```

<br>

In my quest for answers about testing, I also came across a great episode of Go Time [Go Time Podcast](https://changelog.com/gotime/174) which focuses on testing. Based on the discussion it seems TDD is not one size fits all. Sometimes you need to write some skeleton code before you can a get a working set of tests. Another absolute gem I came across was this gitbook [Learn Go With Tests](https://quii.gitbook.io/learn-go-with-tests). It gives really great walkthroughs which I found easy to follow along. 

<br>

Depending on industry, in some places, testing code can be mission critical. I can imagine if your applications and systems are working with financial transactions or highly sensitive data, testing must be incredibly important. I'm going to continue hacking away at the second part of the exercise 1. I'm currently wrapping my head around goroutines and channels as I try to figure out how to keep track of user input while also keeping track of a timer. I'll talk about my findings and solution in a future post. 

Cheers! 👋



