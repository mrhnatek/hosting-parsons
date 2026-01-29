---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Parsons Practice

## Easier problem
Get a student to enter the score and tell them how they have done; don't forget the indentation!

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "score = int(input(&quot;Enter score: &quot;))
\n" +
    "
\n" +
    "if score &gt;= 70:
\n" +
    "    print(&quot;Grade: A&quot;)
\n" +
    "elif score &gt;= 50:
\n" +
    "    print(&quot;Grade: B&quot;)
\n" +
    "else:
\n" +
    "    print(&quot;Grade: C&quot;)";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "python3": true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>


## Parsons 2 (Variable Check Grader)
A cinema charges different prices depending on your age and whether it is a weekend.
The program should ask for the customer’s age, ask if it is a weekend, work out the correct ticket price and then display the final price
Rules:
- Under 12 → £5
- Under 18 → £7
- 18 or over → £10
- If it is a weekend → add £2 to the price

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "age = int(input(&quot;Enter your age: &quot;))
\n" +
    "day = input(&quot;Is it a weekend? (yes/no): &quot;)
\n" +
    "
\n" +
    "price = 10
\n" +
    "
\n" +
    "if age &lt; 12:
\n" +
    "    price = 5
\n" +
    "elif age &lt; 18:
\n" +
    "    price = 7
\n" +
    "else:
\n" +
    "    price = 10
\n" +
    "
\n" +
    "if day == &quot;yes&quot;:
\n" +
    "    price = price + 2
\n" +
    "
\n" +
    "print(&quot;Ticket price:&quot;, price)";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "python3": true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
### Implementation Notes

When you host multiple Parson's problems on a single markdown page, you need to add a unique prefix. You can easily do this in the Codio generator by typing a unique prefix into the "Prefix" textbox and pressing Enter/Return. Then you can simply copy-paste like normal.

If want each problem to be it's own page, you can use relative path links at the bottom of each of your markdown pages as seen below. If you want students to be able to return to previous problems in this format, consider adding previous links or link to a table of contents like page.

### Example Next Link
[Next](./parsons/example1.html)
