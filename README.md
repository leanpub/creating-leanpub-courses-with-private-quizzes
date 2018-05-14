# creating-leanpub-courses

This is an example of how to create a Leanpub course with a public manuscript while keeping the quizzes themselves private.

This is done by using Git Submodules.

There are two repositories. This one is public and cointains the everything but the quizzes.

The second repository contains the quizzes and is private.

Here's a step-by-step procedure to create this:

1) Create the public repository. It is found at https://github.com/leanpub/creating-leanpub-courses-with-private-quizzes.

2) Create the private repository. It is found at https://github.com/spatten/creating-leanpub-courses-quizzes-only.

The Public repository will contain the manuscript and everything but the quizzes. The `Book.txt` file in the public repository refers to the quizzes in a `quizzes` directory which does not exist yet. It looks like this:

```
creating-leanpub-courses.txt
quiz-intro.txt
quizzes/quiz1.txt
quizzes/quiz2.txt
quizzes/quiz3.txt
quizzes/quiz4.txt
quizzes/quiz5.txt
```

The next step is to import the content of the private repository into your public one using Git submodules. Get yourself into the root directory of the "creating-leanpub-courses-with-private-quizzes" repository and do this:

```
git submodule add git@github.com:spatten/creating-leanpub-courses-quizzes-only.git manuscript/quizzes
```

Finally, you need to give Leanpub access to both repositories. On the Settings => Contributors tab for both repositories, invite "Leanpub" (https://github.com/leanpub). We will accept the invitation when you preview the course for the first time.
