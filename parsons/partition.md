---
layout: default
title: Partition (from quick sort)
---

<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "# partition the subarray items[start..end] so that\n" +
    "# items[start..j-1] &lt;= items[j] &lt;= items[j+1..end] and return the index j.\n" +
    "def partition(items, start, end):\n" +
    "    i = start + 1\n" +
    "    j = end\n" +
    "    v = items[start]\n" +
    "    while True:\n" +
    "        # find item on left to swap\n" +
    "        while i &lt;= j and items[i] &lt;= v:\n" +
    "            i = i + 1\n" +
    "\n" +
    "        # find item on right to swap\n" +
    "        while j &gt;= i and items[j] &gt;= v:\n" +
    "            j = j - 1\n" +
    "\n" +
    "        # check if pointers cross\n" +
    "        if (i &gt; j):\n" +
    "            break\n" +
    "\n" +
    "        # swap\n" +
    "        tmp = items[i]\n" +
    "        items[i] = items[j]\n" +
    "        items[j] = tmp\n" +
    "\n" +
    "    # put partitioning item v at items[j]\n" +
    "    tmp = items[start]\n" +
    "    items[start] = items[j]\n" +
    "    items[j] = tmp\n" +
    "\n" +
    "    # now, items[start .. j-1] &lt;= items[j] &lt;= items[j+1 .. end]\n" +
    "    return j";
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

[Home](../index.html)
[Merge (merge sort)](./merge.html)
