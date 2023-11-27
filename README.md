In this article, we will explore how to create an accordion in a PowerApps Canvas Application.

In our application Screen, we will have a container, which contains:
<ul>
 	<li>A horizontal container, with two main components
<ul>
 	<li>The section on the left will contain an HTML text with our help guidelines.</li>
 	<li>A right container which contains an optional image.</li>
</ul>
</li>
 	<li>An accordion text (label)</li>
 	<li>The left help icon</li>
 	<li>An expand button on the far right.</li>
</ul>
&nbsp;

<a href="https://samtech365.com/wp-content/uploads/2023/11/Screenshot-2023-11-27-at-22.03.09.png"><img class="aligncenter size-full wp-image-100793" src="https://samtech365.com/wp-content/uploads/2023/11/Screenshot-2023-11-27-at-22.03.09.png" alt="" style="height:600px" /></a>

The container's height will be dynamic and based on a context variable set when the accordion text or expand button is clicked.
<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="monokai">If(
    varHelpAccordion = true,
    UpdateContext({varHelpAccordion: false}),
    UpdateContext({varHelpAccordion: true})
)</pre>
Now, the accordion height's value is as follows:
<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="monokai">If(varHelpAccordion,Parent.Height - Self.Y*2,48)</pre>
<a href="https://samtech365.com/wp-content/uploads/2023/11/Screenshot-2023-11-27-at-22.08.59.png"><img class="aligncenter size-full wp-image-100794" src="https://samtech365.com/wp-content/uploads/2023/11/Screenshot-2023-11-27-at-22.08.59.png" alt="" style="height:600px" /></a>

What this does, is that it checks the varHelpAccordion value, if it is true (expanded), the container height is calculated dynamically from the (Parent. Height- Self.Y*2) which will ensure that that accordion is vertically centred in the screen, if not (collapsed), it will set the height to 48.
