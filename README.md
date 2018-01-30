# Build a Calendar with HTML &amp; CSS

This is a simple, responsive calendar made with HTML and CSS.

[Read the Article](https://angelajholden.com/build-a-calendar-with-html-css)

I had a project recently where my client wanted a calendar for their site, but didn't want to embed a Google Calendar. They wanted a month at a time view, and wanted to update just a few dates each month. What follows is a simple calendar made with two <code class="language-markup">&lt;ul></code> lists and some CSS. And of course it's responsive.

Let's start with a <code class="language-markup">&lt;ul></code> list for the days of the week.

```markup
<pre><code class="language-markup">
	<ul class="days-of-week clearfix">
		<li>Sunday</li>
		<li>Monday</li>
		<li>Tuesday</li>
		<li>Wednesday</li>
		<li>Thursday</li>
		<li>Friday</li>
		<li>Saturday</li>
	</ul>
</code></pre>
```

Next we need a second <code class="language-markup">&lt;ul></code> list with 35 <code class="language-markup">&lt;li></code>s. Our calendar needs five rows, each with seven days to represent each day of the month.

Each <code class="language-markup">&lt;li></code> has a <code class="language-markup">&lt;span></code> for the date. Beneath the date, I added an event.

<pre><code class="language-markup">
	&lt;ul class="days-of-month clearfix">
		&lt;!-- Week One -->
		&lt;li>
			&lt;span>&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>1&lt;/span>
			First of the month!
		&lt;/li>
		&lt;li>
			&lt;span>2&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>3&lt;/span>
		&lt;/li>

		&lt;!-- Week Two -->
		&lt;li>
			&lt;span>4&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>5&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>6&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>7&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>8&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>9&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>10&lt;/span>
		&lt;/li>

		&lt;!-- Week Three -->
		&lt;li>
			&lt;span>11&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>12&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>13&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>14&lt;/span>
			Valentine's Day
		&lt;/li>
		&lt;li>
			&lt;span>15&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>16&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>17&lt;/span>
		&lt;/li>

		&lt;!-- Week Four -->
		&lt;li>
			&lt;span>18&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>19&lt;/span>
			President's Day
		&lt;/li>
		&lt;li>
			&lt;span>20&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>21&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>22&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>23&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>24&lt;/span>
		&lt;/li>

		&lt;!-- Week Five -->
		&lt;li>
			&lt;span>25&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>26&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>27&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>28&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>&lt;/span>
		&lt;/li>
		&lt;li>
			&lt;span>&lt;/span>
		&lt;/li>
	&lt;/ul>
</code></pre>

Next we need CSS to style the lists and make them into a responsive calendar. Let's start with the days of the week and CSS that will apply to both lists.

<pre><code class="language-css">
	html { /* It's a good idea to have box-sizing: border-box on every element */
	  box-sizing: border-box;
	}

	*, *:before, *:after {
	  box-sizing: inherit;
	}

	.clearfix:after { /* We need this to clear the floats */
	  content: "";
	  display: table;
	  clear: both;
	}

	ul {
	  margin: 0;
	  padding: 0;
	}

	ul li {
	  list-style-type: none;
	  display: block;
	  width: 14.2857143%; /* 100 / 7 = 7 days of the week */
	  float: left;
	}

	.days-of-week li {
	  text-align: center;
	  color: #16a085;
	  background-color: #fff;
	  padding: 10px 0;
	  border-top: 1px solid #fff;
	  border-right: 1px solid #16a085;
	  border-bottom: 1px solid #fff;
	}

	.days-of-week li:first-child {
	  border-left: 1px solid #fff;
	}

	.days-of-week li:last-child {
	  border-right: 1px solid #fff;
	}
</code></pre>

Next let's style the remaining 35 calendar days and get them lined up beneath their respective days.

<pre><code class="language-css">
	.days-of-month li {
	  position: relative; /* We need this to position the spans and dates */
	  padding: 25px 10px;
	  height: 125px; /* Each day has a fixed height */
	  text-align: center;
	  border-top: none;
	  border-right: 1px solid #fff;
	  border-bottom: 1px solid #fff;
	}

	.days-of-month li:nth-of-type(1) {
	  border-left: 1px solid #fff;
	}

	.days-of-month li:nth-of-type(7n+8) {
	  border-left: 1px solid #fff;
	  clear: both; /* Clear the first day of each row */
	}

	.days-of-month li span {
	  /* Position each date in the upper left-hand corner */
	  position: absolute;
	  top: 5px;
	  left: 5px;
	  font-size: 0.8em;
	}
</code></pre>

And finally, let's write some media queries and make this responsive. I'm using 960px as a breakpoint so the calendar will be seen as a grid on an iPad in landscape, and responsive in portrait view.

<pre><code class="language-css">
	@media only screen and (max-width: 960px) {
	  .days-of-week {
	    position: absolute;
	    top: -9999px;
	    left: -9999px;
	  }

	  .days-of-month li {
	    padding: 25px;
	    height: auto;
	    width: 100%;
	    float: none;
	    border-top: none;
	    border-left: none;
	    border-right: none;
	  }

	  .days-of-month li:nth-of-type(1) {
	    border-left: none;
	  }

	  .days-of-month li:nth-of-type(7n+8) {
	    border-left: none;
	    clear: both;
	  }
	  
	  .days-of-month li span {
	    top: 50%;
	    transform: translateY(-50%);
	  }
	}
</code></pre>