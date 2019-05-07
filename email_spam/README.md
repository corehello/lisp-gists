# Usages:
## load deps
```
(ql:quickload :cl-ppcre)
```

## load lisp files
```
CL-USER> (load "email_spam.lisp")
```

## into the pagkage
```
CL-USER> (in-package :com.coreworks.spam)
```

## add directory files to corpus
```
SPAM> (add-directory-to-corpus "spam/" 'spam *corpus*)
NIL
SPAM> (add-directory-to-corpus "easy_ham/" 'ham *corpus*)
NIL
```

## start with the training
```
SPAM>(defparameter *results* (test-classifier *corpus* 0.5d0))
```

## analysis the results
```
SPAM> (analyze-results *result*)
Total:               1526 : 100.00%
Correct:             1512 :  99.08%
False-positive:         0 :   0.00%
False-negative:         4 :   0.26%
Missed-ham:             4 :   0.26%
Missed-spam:            6 :   0.39%
NIL
```

## test the classifier
```
SPAM> (classify "could you help me with some money")
UNSURE
0.4958065868372031d0
SPAM> (classify "could you help me with some money from bank")
SPAM
0.6227735976205515d0
```
