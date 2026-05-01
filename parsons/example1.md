---
layout: default
title: Bubble sort
---

<div id="p1-sortableTrash" class="sortable-code"></div> 
<div id="p1-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="p1-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="p1-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "for i in range(0, len(arr) - 1):
\n" +
    "    for j in range(0, len(arr) - 1):
\n" +
    "        if arr[j] &gt; arr[j + 1]:
\n" +
    "            tmp = arr[j + 1]
\n" +
    "            arr[j + 1] = arr[j]
\n" +
    "            arr[j] = tmp";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p1-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "p1-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p1-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#p1-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>

[Home](../index.html)
