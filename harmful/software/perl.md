# Perl has shitty stuff

Perl functions parameters are funny

<pre style='color:#d1d1d1;'><span style='color:#e66170; font-weight:bold; '>sub</span> function 
<span style='color:#b060b0; '>{</span>
	<span style='color:#e66170; font-weight:bold; '>my</span> <span style='color:#d2cd86; '>(</span>$x<span style='color:#d2cd86; '>,</span> $y<span style='color:#d2cd86; '>)</span> <span style='color:#d2cd86; '>=</span> @_<span style='color:#b060b0; '>;</span>
	<span style='color:#9999a9; '># do something with $x and $y</span>
<span style='color:#b060b0; '>}</span>

<span style='color:#9999a9; '># why can't it be like this?</span>

<span style='color:#e66170; font-weight:bold; '>sub</span> function<span style='color:#d2cd86; '>(</span><span style='color:#ffffff; background:#dd0000; '>m</span><span style='color:#ffffff; background:#dd0000; '>y</span> <span style='color:#ffffff; background:#dd0000; '>$</span><span style='color:#ffffff; background:#dd0000; '>x</span><span style='color:#ffffff; background:#dd0000; '>,</span> <span style='color:#ffffff; background:#dd0000; '>m</span><span style='color:#ffffff; background:#dd0000; '>y</span> <span style='color:#ffffff; background:#dd0000; '>$</span><span style='color:#ffffff; background:#dd0000; '>y</span><span style='color:#d2cd86; '>)</span> 
<span style='color:#b060b0; '>{</span>
	<span style='color:#9999a9; '># do something with $x and $y</span>
<span style='color:#b060b0; '>}</span>
</pre>

### use strict

really? it should be enabled by default. it shold be ```use
unstrict``` instead

### perl's logo is an onion

visiting code you wrote some weeks ago will make you cry.
