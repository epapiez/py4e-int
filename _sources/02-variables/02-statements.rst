Statements
----------

A *statement* is a unit of code that the Python
interpreter can execute. We have seen two kinds of statements: print being
an expression statement and assignment.

When you type a statement in interactive mode, the interpreter executes
it and displays the result, if there is one.

A script usually contains a sequence of statements. If there is more
than one statement, the results appear one at a time as the statements
execute.

For example, run this code to see what it does.

.. activecode:: 02-ac-6-print-vars
  :caption: Assignments and statements in Python

  print(1)
  x = 2
  print(x)


The assignment statement produces no output.


.. mchoice:: 02-mc-6-var3
   :answer_a: dog
   :answer_b: fish
   :answer_c: cat
   :answer_d: bird
   :correct: a
   :feedback_a: Correct! The value of var3 is first set to "bird" but then changed to be the value of var1.  The value of var1 is first set to "cat" but later changed to the value of var2 which was set to "dog".
   :feedback_b: Only var2 has the value of fish.  When you assign the value of a variable to the value of another variable the value is copied to the new variable.  No relationship is created between the two variables.
   :feedback_c: The value of var3 is first set to "bird" but then changed to be the value of var1.  However, the value of var1 also is changed after it is originally set.
   :feedback_d: While var3 is originally set to "bird" the value is changed later.

   What is the value of var3 after the following code executes?

   ::

      var1 = "cat"
      var2 = "dog"
      var3 = "bird"
      var1 = var2
      var3 = var1
      var2 = "fish"

.. mchoice:: 02-mc-7-var2
   :answer_a: dog
   :answer_b: fish
   :answer_c: cat
   :answer_d: bird
   :correct: b
   :feedback_a: The value of var2 is first set to "dog" but then it changes. What does it change to?
   :feedback_b: Correct! The value of var2 is first set to "dog" then changed to "fish". Even though var1 is reassigned to the value of var2 it does not change the value of var2.
   :feedback_c: Var1 is first assigned to the value "cat", what is var2 assigned to?
   :feedback_d: Var3 is initially set to "bird", but "bird" has no relationship to var2. What is var2 assigned to?

   What is the value of var2 after the following code executes?

   ::

      var1 = "cat"
      var2 = "dog"
      var3 = "bird"
      var1 = var2
      var3 = var1
      var2 = "fish"


.. fillintheblank:: 02-fitb-1-statements

    The process of giving value to a variable is called a(n)

    - :^assignment$|^Assignment$|^ASSIGNMENT$: Correct!
      :.*: Reread the text above!

.. clickablearea:: 02-ca-3-statements
  :question: Click the assignments in this codeblock.
  :iscode:
  :feedback: Remember that an assignment gives value to a variable and does not produce output.

  :click-correct:minutes = 60:endclick:
  :click-incorrect:print(minutes):endclick:
  :click-correct:seconds = minutes * 60:endclick:
  :click-incorrect:print("There are " + seconds + " in " + minutes + "."):endclick:
