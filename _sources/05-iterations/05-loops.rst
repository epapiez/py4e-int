Loop patterns
-------------

Often we use a ``for`` or ``while`` loop to go through
a list of items or the contents of a file and we are looking for
something such as the largest or smallest value of the data we scan
through.

These loops are generally constructed by:


*
  Initializing one or more variables before the loop starts

*
  Performing some computation on each item in the loop body, possibly
  changing the variables in the body of the loop

*
  Looking at the resulting variables when the loop completes

We will use a list of numbers to demonstrate the concepts and
construction of these loop patterns.

Counting and summing loops
^^^^^^^^^^^^^^^^^^^^^^^^^^

For example, to count the number of items in a list, we would write the
following ``for`` loop:

.. codelens:: codelens561
    :showoutput:

   count = 0
   for itervar in [3, 41, 12, 9, 74, 15]:
       count = count + 1
   print('Count: ', count)


We set the variable ``count`` to zero before the loop starts,
then we write a ``for`` loop to run through the list of
numbers. Our *iteration* variable is named
``itervar`` and while we do not use ``itervar`` in the
loop, it does control the loop and cause the loop body to be executed
once for each of the values in the list.

.. mchoice:: 05question6_1
   :answer_a: itervar
   :answer_b: count
   :answer_c: Count
   :answer_d: list
   :correct: a
   :feedback_a: Correct!
   :feedback_b: Try again!
   :feedback_c: Try again!
   :feedback_d: Try again!

   Which variable is the iteration variable in the code block?

   .. code-block:: python

    count = 0
    for itervar in [3, 41, 12, 9, 74, 15]:
        count = count + 1
    print('Count: ', count)

In the body of the loop, we add 1 to the current value of
``count`` for each of the values in the list. While the loop is
executing, the value of ``count`` is the number of values we
have seen "so far".

Once the loop completes, the value of ``count`` is the total
number of items. The total number "falls in our lap" at the end of the
loop. We construct the loop so that we have what we want when the loop
finishes.

Another similar loop that computes the total of a set of numbers is as
follows:

.. codelens:: codelens562
    :showoutput:

   total = 0
   for itervar in [3, 41, 12, 9, 74, 15]:
       total = total + itervar
   print('Total: ', total)


In this loop we *do* use the *iteration variable*.
Instead of simply adding one to the ``count`` as in the
previous loop, we add the actual number (3, 41, 12, etc.) to the running
total during each loop iteration. If you think about the variable
``total``\ , it contains the "running total of the values so
far". So before the loop starts ``total`` is zero because we
have not yet seen any values, during the loop ``total`` is the
running total, and at the end of the loop ``total`` is the
overall total of all the values in the list.

As the loop executes, ``total`` accumulates the sum of the
elements; a variable used this way is sometimes called an
*accumulator*.

Neither the counting loop nor the summing loop are particularly useful
in practice because there are built-in functions ``len()`` and
``sum()`` that compute the number of items in a list and the
total of the items in the list respectively.

Maximum and minimum loops
^^^^^^^^^^^^^^^^^^^^^^^^^

To find the largest value in a list or sequence, we
construct the following loop:

.. activecode:: 05section6_1
   :coach:
   :caption: To find the largest value in a list or sequence, we construct the following loop.

   largest = None
   print('Before:', largest)
   for itervar in [3, 41, 12, 9, 74, 15]:
       if largest is None or itervar > largest :
           largest = itervar
       print('Loop:', itervar, largest)
   print('Largest:', largest)


When the program executes, the output is as follows:

.. code-block::

   Before: None
   Loop: 3 3
   Loop: 41 41
   Loop: 12 41
   Loop: 9 41
   Loop: 74 74
   Loop: 15 74
   Largest: 74


The variable ``largest`` is best thought of as the "largest
value we have seen so far". Before the loop, we set ``largest``
to the constant ``None``. ``None`` is a special
constant value which we can store in a variable to mark the variable as
"empty".

Before the loop starts, the largest value we have seen so far is
``None`` since we have not yet seen any values. While the loop
is executing, if ``largest`` is ``None`` then we take
the first value we see as the largest so far. You can see in the first
iteration when the value of ``itervar`` is 3, since
``largest`` is ``None``\ , we immediately set
``largest`` to be 3.

After the first iteration, ``largest`` is no longer
``None``\ , so the second part of the compound logical expression
that checks ``itervar > largest`` triggers only when we see a
value that is larger than the "largest so far". When we see a new "even
larger" value we take that new value for ``largest``. You can
see in the program output that ``largest`` progresses from 3 to
41 to 74.

At the end of the loop, we have scanned all of the values and the
variable ``largest`` now does contain the largest value in the
list.

To compute the smallest number, the code is very similar with one small
change:

.. activecode:: 05section6_2
   :coach:
   :caption: To find the smallest value in a list or sequence, we construct the following loop.

   smallest = None
   print('Before:', smallest)
   for itervar in [3, 41, 12, 9, 74, 15]:
       if smallest is None or itervar < smallest:
           smallest = itervar
       print('Loop:', itervar, smallest)
   print('Smallest:', smallest)


Again, ``smallest`` is the "smallest so far" before, during,
and after the loop executes. When the loop has completed,
``smallest`` contains the minimum value in the list.

Again as in counting and summing, the built-in functions
``max()`` and ``min()`` make writing these exact loops
unnecessary.

The following is a simple version of the Python built-in
``min()`` function:

.. activecode:: 05section6_3
   :coach:
   :caption: A simple version of the Python built-in min() function

   def min(values):
       smallest = None
       for value in values:
           if smallest is None or value < smallest:
               smallest = value
       return smallest

   nums = [1,2,3,4,5]
   print(min(nums))


In the function version of the smallest code, we removed all of the
``print`` statements so as to be equivalent to the
``min`` function which is already built in to Python.
