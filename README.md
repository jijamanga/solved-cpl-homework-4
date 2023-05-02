Download Link: https://assignmentchef.com/product/solved-cpl-homework-4
<br>
In this Homework assignment, we will be writing in ​ <a href="https://franz.com/products/allegrocl/">LIS</a><u>​        </u><a href="https://franz.com/products/allegrocl/">P</a><a href="https://franz.com/products/allegrocl/">.</a><u>​</u> If you need help on how to run LISP on Openlab, refer to this document <a href="https://docs.google.com/document/d/1Vn0H-zGRuSY1-UPH3PiMJo7njIDRIbtcxnaLTvZdO88/edit?usp=sharing">her</a>​         <a href="https://docs.google.com/document/d/1Vn0H-zGRuSY1-UPH3PiMJo7njIDRIbtcxnaLTvZdO88/edit?usp=sharing">e</a><a href="https://docs.google.com/document/d/1Vn0H-zGRuSY1-UPH3PiMJo7njIDRIbtcxnaLTvZdO88/edit?usp=sharing">.</a><u>​</u>

<strong> </strong>

In writing the following LISP functions, you may use only these primitive functions:




<table width="424">

 <tbody>

  <tr>

   <td width="24">●●●●●●</td>

   <td width="288">defun cond cons car cdr operators +, -, &lt;, and &gt;</td>

   <td width="24"> </td>

   <td width="24">●●●●●</td>

   <td width="64">null eqlistpatom symbolp</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

You may also write and use auxiliary functions, but you must submit these along with your solution. HINT: some functions require subfunctions.




<strong>NOTE: </strong>​ You MUST use recursion instead of looping. DO NOT assume the lists are SIMPLE​    unless it is explicitly specified in the problem statement.




<strong>EFFICIENCY NOTE:</strong> ​ <u>Do not traverse the whole list more than once</u>​         . For example, do not<u>​        </u> flatten the list before processing it. Please provide sample runs that adequately test the functionality of each function.

<strong> </strong>

We will start by writing some built-in functions, but we will add “my_” (or “my-”) to the front of the name. I tried to put these in order of difficulty (IMO). <u>The first two are for practice and not</u>​   <u>worth any points, but please show them working correctly in your report<strong>.</strong></u><u>​</u>

<strong> </strong>

<ol>

 <li><strong>[</strong><strong>8</strong>​ <strong>]</strong>​ Define a function​ <strong> my-length</strong>​   that takes one parameter, a list L, and returns the​      number of top-level elements in L. Examples:

  <ul>

   <li>(my-length nil) –&gt; 0</li>

  </ul></li>

</ol>

<strong>○ </strong>(my-length ‘(b (a b c))       –&gt; 2

<strong>○ </strong>(my-length ‘(a (((b))) c))    –&gt; 3

<strong>○ </strong>(my-length ‘(a b c))          –&gt; 3

<strong>             </strong>

<ol start="2">

 <li><strong>[</strong><strong>10</strong>​ <strong>]</strong>​ Define a function ​  <strong>my-memq</strong>​    that takes two parameters, a symbol A and a list of​    symbols L, and returns the list starting where the symbol bound to A was found.   It returns nil otherwise.  Examples:

  <ul>

   <li>(my-memq ‘a nil) –&gt; nil</li>

  </ul></li>

</ol>

○ (my-memq ‘b ‘(a b c))         –&gt; (b c)

○ (my-memq ‘d ‘(a b c d e f g)) –&gt; (d e f g)

○ (my-memq ‘d ‘(a b c d))        –&gt; (d)

○ (my-memq ‘d ‘(a b c))          –&gt; nil




<ol start="3">

 <li><strong>[</strong><strong>8</strong>​ <strong>]</strong>​ Define a function ​ <strong>my-append</strong>​  that takes two parameters, a list L1 and a list L2, and​ returns the result of appending the two lists together.  You must not call append.

  <ul>

   <li>(my-append ‘(a b c) ‘(d e f))</li>

  </ul></li>

</ol>

–&gt; (a b c d e f)

○ (my-append ‘((a) (b) (c)) ‘((d) (e) (f)))

–&gt; ((a) (b) (c) (d) (e) (f))

○ (my-append nil ‘(d e f))

–&gt; (d e f)

○ (my-append ‘(a b c) nil)

–&gt; (a b c)




<ol start="4">

 <li><strong>[</strong><strong>6</strong>​ <strong>]</strong>​ Define the function ​ <strong>my-attach</strong>​    which takes an object O and a list L and returns the​   list L with O added to the end. Examples:

  <ul>

   <li>(my-attach ‘a nil) –&gt; (a)</li>

  </ul></li>

</ol>

○ (my-attach ‘d ‘(a b c))        –&gt; (a b c d)

○ (my-attach ‘(a) ‘(b c))        –&gt; (b c (a))




<ol start="5">

 <li><strong>[</strong><strong>10</strong>​ <strong>]</strong>​ Define the function ​        <strong>my-assoc</strong>​    that takes an atom A and a list L and returns the​       association pair for A. L is of the form ((key1 . value1)(key2 . value2) … (keyn . valuen)) Examples:

  <ul>

   <li>(my-assoc ‘a nil) –&gt; nil</li>

  </ul></li>

</ol>

○ (my-assoc ‘a ‘((a . b)(c e f)(b))) –&gt; (a . b) ○ (my-assoc ‘c ‘((a . b)(c e f)(b))) –&gt; (c e f)

○ (my-assoc ‘b ‘((a . b)(c e f)(b))) –&gt; (b)

○ (my-assoc ‘f ‘((a . b)(c e f)(b))) –&gt; nil




<ol start="6">

 <li><strong>[</strong><strong>6</strong>​ <strong>]</strong>​ Define the function ​ <strong>freq</strong>​   that takes a symbol A and a list L and counts the​       occurrence of symbol A found anywhere in L. Examples:

  <ul>

   <li>(freq ‘c ‘((a c) c e))  –&gt; 2 ○ (freq  ‘f ‘(((s) o ) d))      –&gt; 0</li>

  </ul></li>

</ol>

○ (freq  ‘f ‘(((f) f) f f))     –&gt; 4

<ol start="7">

 <li><strong>[</strong><strong>6</strong>​ <strong>]</strong>​ Define the function ​ <strong>mapping</strong>​      that takes 2 arguments – a list L, and an integer value​ Every element of the list L is a list of two atoms – key and object. (e.g. L &lt;– ((35 kim) (67 clinton) (45 emma))) The function returns a list of objects whose key is less than val. Examples:

  <ul>

   <li>(mapping ‘((35 kim) (67 clinton) (45 emma)) 40)  –&gt; (kim)</li>

  </ul></li>

</ol>

○ (mapping ‘((24 a) (15 b) (56 c) (19 d)) 26)    –&gt; (a b d)

○ (mapping ‘((90 a) (80 b) (70 c))  40)

–&gt; nil




<ol start="8">

 <li><strong>[</strong><strong>10</strong>​ <strong>]</strong>​ Define a function ​  <strong>my-last</strong>​        that takes two parameters, a symbol A and a list of​    symbols L, and returns the list starting where the last occurrence of symbol A is in L.  It returns nil only if A is not in the list.  Examples:</li>

</ol>

<table width="466">

 <tbody>

  <tr>

   <td width="24">○</td>

   <td width="442">(my-last ‘a ‘(a b c a b c a b c d e f g))–&gt;    (a b c d e f g)</td>

  </tr>

  <tr>

   <td width="24">○</td>

   <td width="442">(my-last ‘b ‘(a b c a b c a b c d e f g))–&gt;    (b c d e f g)</td>

  </tr>

  <tr>

   <td width="24">○</td>

   <td width="442">(my-last ‘c ‘(a b c a b c a b c d e f g))–&gt;    (c d e f g)</td>

  </tr>

  <tr>

   <td width="24">○</td>

   <td width="442">(my-last ‘g ‘(a b c a b c a b c d e f g))–&gt;    (g)</td>

  </tr>

  <tr>

   <td width="24">○</td>

   <td width="442">(my-last ‘h ‘(a b c a b c a b c d e f g))</td>

  </tr>

 </tbody>

</table>

–&gt;    nil




<ol start="9">

 <li><strong>[</strong><strong>8</strong>​ <strong>]</strong>​ Define the function ​ <strong>my-reverse</strong>​  that takes a list L and returns the reverse of L.​ Examples:

  <ul>

   <li>(my-reverse nil) –&gt; nil</li>

  </ul></li>

</ol>

○ (my-reverse ‘(a))                   –&gt; (a)

○ (my-reverse ‘(1 2 3 4 5))           –&gt; (5 4 3 2 1)

○ (my-reverse ‘((1 2 3) 4 ((5 6))))  –&gt; (((5 6)) 4 (1 2 3))

<strong>             </strong>

<strong>10.[</strong><strong>8</strong>​ <strong>]</strong>​ Define the function ​     <strong>is-pattern?</strong>​   that takes two SIMPLE lists pat and str and returns​    the sublist of str which starts with the pat if pat is a substring of str. Otherwise, it returns nil. Examples:

○ (is-pattern? ‘(a b s) ‘(c d b a s))

–&gt; nil

○ (is-pattern? ‘(c a c) ‘(b a j a c a c t u s))

–&gt; (c a c t u s)

○ (is-pattern? nil ‘(a n y l i s t))

–&gt; nil

○ (is-pattern? ‘(l i s p) nil)

–&gt; nil




<strong>11.[</strong><strong>8</strong>​ <strong>]</strong>​ Define the function ​     <strong>first-atom</strong>​    that takes a list L and returns the first atom of L.​        Examples:

○ (first-atom nil)                   –&gt; nil

○ (first-atom ‘((2 (1) 4) 6))    –&gt; 2 ○ (first-atom ‘((((s)) o )))         –&gt; s

○ (first-atom ‘(1 (((2)) 3 4)))       –&gt; 1




<strong>12.[10] </strong>Define a function ​       <strong>find-all</strong>​        that takes a symbol A and a list L and finds and returns​       the first symbol following each occurrence of A in L, or nil if A does not occur in L. Note that A may occur nested within L, possibly as the last element of a sublist.  You may assume that there is always a symbol occurring afterwards. Examples:

○ (find-all ‘a nil)                  –&gt; nil

○ (find-all ‘a ‘(b a c a e))         –&gt; (c e) ○ (find-all ‘a ‘(b d c e))           –&gt; nil

○ (find-all ‘a ‘(b (a a) c))         –&gt; (a c)

○ (find-all ‘a ‘((b a) ((c a b))))   –&gt; (c b)

<strong> </strong>