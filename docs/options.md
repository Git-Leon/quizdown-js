# Options

Options can be set globally, per quiz or even per question. Options on the quiz level overwrite global options. 

## Setting global options

Currently, the following options are supported. Shown are the default settings:

```typescript
let config = {
	start_on_load: true,		 // detect and convert all divs with class quizdown
    shuffle_answers: true,		 // shuffle answers for each question
    shuffle_questions: false,    // shuffle questsions for each quiz
    primary_color: 'steelblue',  // primary CSS color
    secondary_color: '#f2f2f2',  // secondary CSS color
    text_color: 'black',         // text color of some elements
    locale: null                 // language of the user interface ('en' and 'de' supported)
};

quizdown.init(config);
```

## Language settings

Currently german and english is supported. If `locale: null` the language is fetched from the browser settings.
Otherwise locale can be set to `locale: 'en'` or `locale: 'de'`. 

## Setting quiz and question specific options

- Quiz and question specific options can be set inside the quizdown using YAML headers.
- Only the option `shuffle_answers` can be used on a question level. 
- The answers for sequence questions are always shuffled.


Here is an example:

```markdown
---
primary_color: '#FF851B'
secondary_color: '#DDDDDD'
text_color: black
locale: de
---

# What is the capital of Berlin?

---
shuffle_answers: false
---

In this question you are asked a **very** difficult question.

> Do some research!

-   [x] Berlin
-   [ ] Stuttgart
-   [ ] Cologne
-   [ ] Düsseldorf
```
