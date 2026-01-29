---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Parsons Practice

## Easier problem
Get a student to enter the score and tell them how they have done; don't forget the indentation!
<div id="easy-sortableTrash" class="sortable-code"></div> 
<div id="easy-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="easy-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="easy-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "score = int(input(&quot;Enter score: &quot;))
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
    "sortableId": "easy-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "python3": true,
    "trashId": "easy-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#easy-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#easy-feedbackLink").click(function(event){ 
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

<div id="harder-sortableTrash" class="sortable-code"></div> 
<div id="harder-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="harder-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="harder-newInstanceLink" value="Reset Problem" type="button" /> 
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
    "sortableId": "harder-sortable",
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
  $("#harder-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#harder-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
