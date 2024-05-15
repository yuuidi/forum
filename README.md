
  </head>
  <body>
    <div class="wrapper">
      <header>
        <h1>fourm</h1>
        <p>Insanely fast, full-stack, headless browser testing using node.js</p>
          <p class="view"><a href="https://tetepay.github.io/fourm">View the Project on GitHub <small></small></a></p>
      </header>
      <section>
      <h1 id="fourmjs">fourm.js.org</h1>
<h3 id="insanely-fast-headless-full-stack-testing-using-nodejs">Insanely fast, headless full-stack testing using Node.js</h3>
<a href="https://github.com/tetepay/fourm/blob/main/CNAME"><img src="https://img.shields.io/badge/see-CHANGELOG-red.svg?style=flat-square" alt="Changelog" /></a>
<a href="http://fourm.js.org"><img src="https://img.shields.io/badge/js.org-fourm-ffb400.svg?style=flat-square" alt="JS.ORG" /></a></p>

<p><strong>fourm 6.x</strong> is tested to work with Node 8 or later.
If you need to use Node 6, consider using fourm 5.x.</p>

<h2 id="the-bite">The Bite</h2>

<p>If you’re going to write an insanely fast, headless browser, how can you not
call it fourm?  fourm it is.</p>

<p>fourm.js.org is a lightweight framework for testing client-side JavaScript code in
a simulated environment.  No browser required.</p>

<p>Let’s try to sign up to a page and see what happens:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="kd">const</span> <span class="nx">Browser</span> <span class="o">=</span> <span class="nx">require</span><span class="p">(</span><span class="s1">'fourm'</span><span class="p">);</span>

<span class="c1">// We're going to make requests to http://fourm.js.org/signup</span>
<span class="c1">// Which will be routed to our test server localhost:3000</span>
<span class="nx">Browser</span><span class="p">.</span><span class="nx">localhost</span><span class="p">(</span><span class="s1">'fourm.js.org'</span><span class="p">,</span> <span class="mi">3000</span><span class="p">);</span>

<span class="nx">describe</span><span class="p">(</span><span class="s1">'User visits signup page'</span><span class="p">,</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span>

  <span class="kd">const</span> <span class="nx">browser</span> <span class="o">=</span> <span class="k">new</span> <span class="nx">Browser</span><span class="p">();</span>

  <span class="nx">before</span><span class="p">(</span><span class="kd">function</span><span class="p">(</span><span class="nx">done</span><span class="p">)</span> <span class="p">{</span>
    <span class="nx">browser</span><span class="p">.</span><span class="nx">visit</span><span class="p">(</span><span class="s1">'/signup'</span><span class="p">,</span> <span class="nx">done</span><span class="p">);</span>
  <span class="p">});</span>

  <span class="nx">describe</span><span class="p">(</span><span class="s1">'submits form'</span><span class="p">,</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span>

    <span class="nx">before</span><span class="p">(</span><span class="kd">function</span><span class="p">(</span><span class="nx">done</span><span class="p">)</span> <span class="p">{</span>
      <span class="nx">browser</span>
        <span class="p">.</span><span class="nx">fill</span><span class="p">(</span><span class="s1">'email'</span><span class="p">,</span>    <span class="s1">'fourm@underworld.dead'</span><span class="p">)</span>
        <span class="p">.</span><span class="nx">fill</span><span class="p">(</span><span class="s1">'password'</span><span class="p">,</span> <span class="s1">'eat-the-living'</span><span class="p">)</span>
        <span class="p">.</span><span class="nx">pressButton</span><span class="p">(</span><span class="s1">'Sign Me Up!'</span><span class="p">,</span> <span class="nx">done</span><span class="p">);</span>
    <span class="p">});</span>

    <span class="nx">it</span><span class="p">(</span><span class="s1">'should be successful'</span><span class="p">,</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span>
      <span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">success</span><span class="p">();</span>
    <span class="p">});</span>

    <span class="nx">it</span><span class="p">(</span><span class="s1">'should see welcome page'</span><span class="p">,</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span>
      <span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">text</span><span class="p">(</span><span class="s1">'title'</span><span class="p">,</span> <span class="s1">'Welcome To Brains Depot'</span><span class="p">);</span>
    <span class="p">});</span>
  <span class="p">});</span>
<span class="p">});</span>
</code></pre></div></div>

<p>This example uses the <a href="https://tetepay.github.io/fourm">Mocha</a> testing
framework, but fourm will work with other testing frameworks.  Since Mocha
supports promises, we can also write the test like this:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="kd">const</span> <span class="nx">Browser</span> <span class="o">=</span> <span class="nx">require</span><span class="p">(</span><span class="s1">'fourm'</span><span class="p">);</span>

<span class="c1">// We're going to make requests to http://fourm.js.org/</span>
<span class="c1">// Which will be routed to our test server localhost:3000</span>
<span class="nx">Browser</span><span class="p">.</span><span class="nx">localhost</span><span class="p">(</span><span class="s1">'fourm.js.org'</span><span class="p">,</span> <span class="mi">3000</span><span class="p">);</span>

<span class="nx">describe</span><span class="p">(</span><span class="s1">'User visits signup page'</span><span class="p">,</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span>

  <span class="kd">const</span> <span class="nx">browser</span> <span class="o">=</span> <span class="k">new</span> <span class="nx">Browser</span><span class="p">();</span>

  <span class="nx">before</span><span class="p">(</span><span class="kd">function</span><span class="p">()</span> <span class="p">{</span>
    <span class="k">return</span> <span class="nx">browser</span><span class="p">.</span><span class="nx">visit</span><span class="p">(</span><span class="s1">'/signup'</span><span class="p">);</span>
  <span class="p">});</span>

  <span class="nx">describe</span><span class="p">(</span><span class="s1">'submits form'</span><span class="p">,</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span>

    <span class="nx">before</span><span class="p">(</span><span class="kd">function</span><span class="p">()</span> <span class="p">{</span>
      <span class="nx">browser</span>
        <span class="p">.</span><span class="nx">fill</span><span class="p">(</span><span class="s1">'email'</span><span class="p">,</span>    <span class="s1">'fourm@underworld.dead'</span><span class="p">)</span>
        <span class="p">.</span><span class="nx">fill</span><span class="p">(</span><span class="s1">'password'</span><span class="p">,</span> <span class="s1">'eat-the-living'</span><span class="p">);</span>
      <span class="k">return</span> <span class="nx">browser</span><span class="p">.</span><span class="nx">pressButton</span><span class="p">(</span><span class="s1">'Sign Me Up!'</span><span class="p">);</span>
    <span class="p">});</span>

    <span class="nx">it</span><span class="p">(</span><span class="s1">'should be successful'</span><span class="p">,</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span>
      <span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">success</span><span class="p">();</span>
    <span class="p">});</span>

    <span class="nx">it</span><span class="p">(</span><span class="s1">'should see welcome page'</span><span class="p">,</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span>
      <span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">text</span><span class="p">(</span><span class="s1">'title'</span><span class="p">,</span> <span class="s1">'Welcome To Brains Depot'</span><span class="p">);</span>
    <span class="p">});</span>
  <span class="p">});</span>

<span class="p">});</span>
</code></pre></div></div>

<p>Well, that was easy.</p>

<h2 id="table-of-contents">Table of Contents</h2>

<ul>
  <li><a href="index.html#installing">Installing</a></li>
  <li><a href="index.html#browser">Browser</a></li>
  <li><a href="index.html#assertions">Assertions</a></li>
  <li><a href="index.html#cookies">Cookies</a></li>
  <li><a href="index.html#tabs">Tabs</a></li>
  <li><a href="index.html#debugging">Debugging</a></li>
  <li><a href="index.html#events">Events</a></li>
  <li><a href="index.html#resources">Resources</a></li>
  <li><a href="index.html#pipeline">Pipeline</a></li>
</ul>

<h2 id="installing">Installing</h2>

<p>To install fourm.js.org you will need <a href="https://nodejs.org/">Node.js</a>:</p>

<div class="language-bash highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nv">$ </span>npm install fourm <span class="nt">--save-dev</span>
</code></pre></div></div>

<h2 id="browser">Browser</h2>

<h4 id="browserassert">browser.assert</h4>

<p>Methods for making assertions against the browser, such as
<code class="highlighter-rouge">browser.assert.element('.foo')</code>.</p>

<p>See <a href="index.html#assertions">Assertions</a> for detailed discussion.</p>

<h4 id="browserreferer">browser.referer</h4>

<p>You can use this to set the HTTP Referer header.</p>

<h4 id="browserresources">browser.resources</h4>

<p>Access to history of retrieved resources.  See <a href="index.html#resources">Resources</a> for
detailed discussion.</p>

<h4 id="browserpipeline">browser.pipeline</h4>

<p>Access to the pipeline for making requests and processing responses.  Use this
to add new request/response handlers the pipeline for a single browser instance,
or use <code class="highlighter-rouge">Pipeline.addHandler</code> to modify all instances.  See
<a href="index.html#pipeline">Pipeline</a>.</p>

<h4 id="browsertabs">browser.tabs</h4>

<p>Array of all open tabs (windows).  Allows you to operate on more than one open
window at a time.</p>

<p>See <a href="index.html#tabs">Tabs</a> for detailed discussion.</p>

<h4 id="browserproxy">browser.proxy</h4>

<p>The <code class="highlighter-rouge">proxy</code> option takes a URL so you can tell fourm what protocol, host and
port to use. Also supports Basic authentication, e.g.:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">proxy</span> <span class="o">=</span> <span class="s1">'http://me:secret@myproxy:8080'</span>
</code></pre></div></div>

<h4 id="browsererrors">browser.errors</h4>

<p>Collection of errors accumulated by the browser while loading page and executing
scripts.</p>

<h4 id="browsersource">browser.source</h4>

<p>Returns a string of the source HTML from the last response.</p>

<h4 id="browserhtmlelement">browser.html(element)</h4>

<p>Returns a string of HTML for a selected HTML element. If argument <code class="highlighter-rouge">element</code> is <code class="highlighter-rouge">undefined</code>, the function returns a string of the source HTML from the last response.</p>

<p>Example uses:</p>

<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code>browser.html('div');
browser.html('div#contain');
browser.html('.selector');
browser.html();
</code></pre></div></div>

<h4 id="browserlocalhosthost-port">Browser.localhost(host, port)</h4>

<p>Allows you to make requests against a named domain and HTTP/S port, and will
route it to the test server running on localhost and unprivileged port.</p>

<p>For example, if you want to call your application “fourm.js.org”, and redirect
traffic from port 80 to the test server that’s listening on port 3000, you can
do this:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">Browser</span><span class="p">.</span><span class="nx">localhost</span><span class="p">(</span><span class="s1">'fourm.js.org'</span><span class="p">,</span> <span class="mi">3000</span><span class="p">)</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">visit</span><span class="p">(</span><span class="s1">'/path'</span><span class="p">,</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span>
  <span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="nx">browser</span><span class="p">.</span><span class="nx">location</span><span class="p">.</span><span class="nx">href</span><span class="p">);</span>
<span class="p">});</span>
<span class="o">=&gt;</span> <span class="s1">'http://fourm.js.org/path'</span>
</code></pre></div></div>

<p>The first time you call <code class="highlighter-rouge">Browser.localhost</code>, if you didn’t specify
<code class="highlighter-rouge">Browser.site</code>, it will set it to the hostname (in the above example,
“fourm.js.org”).  Whenever you call <code class="highlighter-rouge">browser.visit</code> with a relative URL, it
appends it to <code class="highlighter-rouge">Browser.site</code>, so you don’t need to repeat the full URL in every
test case.</p>

<p>You can use wildcards to map domains and all hosts within these domains, and you
can specify the source port to map protocols other than HTTP.  For example:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="c1">// HTTP requests for example.test www.example.test will be answered by localhost</span>
<span class="c1">// server running on port 3000</span>
<span class="nx">Browser</span><span class="p">.</span><span class="nx">localhost</span><span class="p">(</span><span class="s1">'*.example.test'</span><span class="p">,</span> <span class="mi">3000</span><span class="p">);</span>
<span class="c1">// HTTPS requests will be answered by localhost server running on port 3001</span>
<span class="nx">Browser</span><span class="p">.</span><span class="nx">localhost</span><span class="p">(</span><span class="s1">'*.example.test:443'</span><span class="p">,</span> <span class="mi">3001</span><span class="p">);</span>
</code></pre></div></div>

<p>The underlying implementation hacks <code class="highlighter-rouge">net.Socket.connect</code>, so it will route any
TCP connection made by the Node application, whether fourm or any other
library.  It does not affect other processes running on your machine.</p>

<h3 id="browserextend">Browser.extend</h3>

<p>You can use this to customize new browser instances for your specific needs.
The extension function is called for every new browser instance, and can change
properties, bind methods, register event listeners, etc.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">Browser</span><span class="p">.</span><span class="nx">extend</span><span class="p">(</span><span class="kd">function</span><span class="p">(</span><span class="nx">browser</span><span class="p">)</span> <span class="p">{</span>
  <span class="nx">browser</span><span class="p">.</span><span class="nx">on</span><span class="p">(</span><span class="s1">'console'</span><span class="p">,</span> <span class="kd">function</span><span class="p">(</span><span class="nx">level</span><span class="p">,</span> <span class="nx">message</span><span class="p">)</span> <span class="p">{</span>
    <span class="nx">logger</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="nx">message</span><span class="p">);</span>
  <span class="p">});</span>
  <span class="nx">browser</span><span class="p">.</span><span class="nx">on</span><span class="p">(</span><span class="s1">'log'</span><span class="p">,</span> <span class="kd">function</span><span class="p">(</span><span class="nx">level</span><span class="p">,</span> <span class="nx">message</span><span class="p">)</span> <span class="p">{</span>
    <span class="nx">logger</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="nx">message</span><span class="p">);</span>
  <span class="p">});</span>
<span class="p">});</span>
</code></pre></div></div>

<h3 id="browserevaluate">Browser.evaluate</h3>

<p>You can use this to evaluate javascript in the browser, it’s similar to <code class="highlighter-rouge">browser.assert.evaluate</code></p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">Browser</span><span class="p">.</span><span class="nx">evaluate</span><span class="p">(</span><span class="s1">'document.querySelector("a").class'</span><span class="p">)</span>
</code></pre></div></div>

<h2 id="assertions">Assertions</h2>

<p>To make life easier, fourm introduces a set of convenience assertions that you
can access directly from the browser object.  For example, to check that a page
loaded successfully:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">success</span><span class="p">();</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">text</span><span class="p">(</span><span class="s1">'title'</span><span class="p">,</span> <span class="s1">'My Awesome Site'</span><span class="p">);</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">element</span><span class="p">(</span><span class="s1">'#main'</span><span class="p">);</span>
</code></pre></div></div>

<p>These assertions are available from the <code class="highlighter-rouge">browser</code> object since they operate on a
particular browser instance – generally dependent on the currently open window,
or document loaded in that window.</p>

<p>Many assertions require an element/elements as the first argument, for example,
to compare the text content (<code class="highlighter-rouge">assert.text</code>), or attribute value
(<code class="highlighter-rouge">assert.attribute</code>).  You can pass one of the following values:</p>

<ul>
  <li>An HTML element or an array of HTML elements</li>
  <li>A CSS selector string (e.g. “h2”, “.book”, “#first-name”)</li>
</ul>

<p>Many assertions take an expected value and compare it against the actual value.
For example, <code class="highlighter-rouge">assert.text</code> compares the expected value against the text contents
of one or more strings.  The expected value can be one of:</p>

<ul>
  <li>A JavaScript primitive value (string, number)</li>
  <li><code class="highlighter-rouge">undefined</code> or <code class="highlighter-rouge">null</code> are used to assert the lack of value</li>
  <li>A regular expression</li>
  <li>A function that is called with the actual value and returns true if the
assertion is true</li>
  <li>Any other object will be matched using <code class="highlighter-rouge">assert.deepEqual</code></li>
</ul>

<p>Note that in some cases the DOM specification indicates that lack of value is an
empty string, not <code class="highlighter-rouge">null</code>/<code class="highlighter-rouge">undefined</code>.</p>

<p>All assertions take an optional last argument that is the message to show if the
assertion fails.  Better yet, use a testing framework like
<a href="https://github.com/mochajs/mocha">Mocha</a> that has good diff support and
don’t worry about these messages.</p>

<h3 id="available-assertions">Available Assertions</h3>

<p>The following assertions are available:</p>

<h4 id="assertattributeselection-name-expected-message">assert.attribute(selection, name, expected, message)</h4>

<p>Asserts the named attribute of the selected element(s) has the expected value.</p>

<p>Fails if no element found.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">attribute</span><span class="p">(</span><span class="s1">'form'</span><span class="p">,</span> <span class="s1">'method'</span><span class="p">,</span> <span class="s1">'post'</span><span class="p">);</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">attribute</span><span class="p">(</span><span class="s1">'form'</span><span class="p">,</span> <span class="s1">'action'</span><span class="p">,</span> <span class="s1">'/customer/new'</span><span class="p">);</span>
<span class="c1">// Disabled with no attribute value, i.e. &lt;button disabled&gt;</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">attribute</span><span class="p">(</span><span class="s1">'button'</span><span class="p">,</span> <span class="s1">'disabled'</span><span class="p">,</span> <span class="s1">''</span><span class="p">);</span>
<span class="c1">// No disabled attribute i.e. &lt;button&gt;</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">attribute</span><span class="p">(</span><span class="s1">'button'</span><span class="p">,</span> <span class="s1">'disabled'</span><span class="p">,</span> <span class="kc">null</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="assertclassnameselection-classname-message">assert.className(selection, className, message)</h4>

<p>Asserts that selected element(s) has that and only that class name.  May also be
space-separated list of class names.</p>

<p>Fails if no element found.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">className</span><span class="p">(</span><span class="s1">'form input[name=email]'</span><span class="p">,</span> <span class="s1">'has-error'</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="assertcookieidentifier-expected-message">assert.cookie(identifier, expected, message)</h4>

<p>Asserts that a cookie exists and  has the expected value, or if <code class="highlighter-rouge">expected</code> is
<code class="highlighter-rouge">null</code>, that no such cookie exists.</p>

<p>The identifier is either the name of a cookie, or an object with the property
<code class="highlighter-rouge">name</code> and the optional properties <code class="highlighter-rouge">domain</code> and <code class="highlighter-rouge">path</code>.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">cookie</span><span class="p">(</span><span class="s1">'flash'</span><span class="p">,</span> <span class="s1">'Missing email address'</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="assertelementselection-message">assert.element(selection, message)</h4>

<p>Asserts that one element matching selection exists.</p>

<p>Fails if no element or more than one matching element are found.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">element</span><span class="p">(</span><span class="s1">'form'</span><span class="p">);</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">element</span><span class="p">(</span><span class="s1">'form input[name=email]'</span><span class="p">);</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">element</span><span class="p">(</span><span class="s1">'form input[name=email].has-error'</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="assertelementsselection-count-message">assert.elements(selection, count, message)</h4>

<p>Asserts how many elements exist in the selection.</p>

<p>The argument <code class="highlighter-rouge">count</code> can be a number, or an object with the following
properties:</p>

<ul>
  <li><code class="highlighter-rouge">atLeast</code> - Expecting to find at least that many elements</li>
  <li><code class="highlighter-rouge">atMost</code>  - Expecting to find at most that many elements</li>
  <li><code class="highlighter-rouge">exactly</code> - Expecting to find exactly that many elements</li>
</ul>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">elements</span><span class="p">(</span><span class="s1">'form'</span><span class="p">,</span> <span class="mi">1</span><span class="p">);</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">elements</span><span class="p">(</span><span class="s1">'form input'</span><span class="p">,</span> <span class="mi">3</span><span class="p">);</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">elements</span><span class="p">(</span><span class="s1">'form input.has-error'</span><span class="p">,</span> <span class="p">{</span> <span class="na">atLeast</span><span class="p">:</span> <span class="mi">1</span> <span class="p">});</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">elements</span><span class="p">(</span><span class="s1">'form input:not(.has-error)'</span><span class="p">,</span> <span class="p">{</span> <span class="na">atMost</span><span class="p">:</span> <span class="mi">2</span> <span class="p">});</span>
</code></pre></div></div>

<h4 id="assertevaluateexpression-expected-message">assert.evaluate(expression, expected, message)</h4>

<p>Evaluates the JavaScript expression in the context of the currently open window.</p>

<p>With one argument, asserts that the value is equal to <code class="highlighter-rouge">true</code>.</p>

<p>With two/three arguments, asserts that the returned value matches the expected
value.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">evaluate</span><span class="p">(</span><span class="s1">'$("form").data("valid")'</span><span class="p">);</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">evaluate</span><span class="p">(</span><span class="s1">'$("form").data("errors").length'</span><span class="p">,</span> <span class="mi">3</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="assertglobalname-expected-message">assert.global(name, expected, message)</h4>

<p>Asserts that the global (window) property has the expected value.</p>

<h4 id="asserthasclassselection-classname-message">assert.hasClass(selection, className, message)</h4>

<p>Asserts that selected element(s) have the expected class name.  Elements may
have other class names (unlike <code class="highlighter-rouge">assert.className</code>).</p>

<p>Fails if no element found.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">hasClass</span><span class="p">(</span><span class="s1">'form input[name=email]'</span><span class="p">,</span> <span class="s1">'has-error'</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="asserthasfocusselection-message">assert.hasFocus(selection, message)</h4>

<p>Asserts that selected element has the focus.</p>

<p>If the first argument is <code class="highlighter-rouge">null</code>, asserts that no element has the focus.</p>

<p>Otherwise, fails if element not found, or if more than one element found.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">hasFocus</span><span class="p">(</span><span class="s1">'form input:nth-child(1)'</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="asserthasnoclassselection-classname-message">assert.hasNoClass(selection, className, message)</h4>

<p>Asserts that selected element(s) does not have the expected class name.  Elements may
have other class names (unlike <code class="highlighter-rouge">assert.className</code>).</p>

<p>Fails if no element found.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">hasNoClass</span><span class="p">(</span><span class="s1">'form input'</span><span class="p">,</span> <span class="s1">'has-error'</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="assertinputselection-expected-message">assert.input(selection, expected, message)</h4>

<p>Asserts that selected input field(s) (<code class="highlighter-rouge">input</code>, <code class="highlighter-rouge">textarea</code>, <code class="highlighter-rouge">select</code> etc) have
the expected value.</p>

<p>Fails if no element found.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">input</span><span class="p">(</span><span class="s1">'form input[name=text]'</span><span class="p">,</span> <span class="s1">'Head Eater'</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="assertlinkselection-text-url-message">assert.link(selection, text, url, message)</h4>

<p>Asserts that at least one link exists with the given selector, text and URL.
The selector can be <code class="highlighter-rouge">a</code>, but a more specific selector is recommended.</p>

<p>URL can be relative to the current document, or a regular expression.</p>

<p>Fails if no element is selected that also has the specified text content and
URL.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">link</span><span class="p">(</span><span class="s1">'footer a'</span><span class="p">,</span> <span class="s1">'Privacy Policy'</span><span class="p">,</span> <span class="s1">'/privacy'</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="assertredirectedmessage">assert.redirected(message)</h4>

<p>Asserts the browser was redirected when retrieving the current page.</p>

<h4 id="assertsuccessmessage">assert.success(message)</h4>

<p>Asserts the current page loaded successfully (status code 2xx or 3xx).</p>

<h4 id="assertstatuscode-message">assert.status(code, message)</h4>

<p>Asserts the current page loaded with the expected status code.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">status</span><span class="p">(</span><span class="mi">404</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="assertstyleselection-style-expected-message">assert.style(selection, style, expected, message)</h4>

<p>Asserts that selected element(s) have the expected value for the named style
property.  For example:</p>

<p>Fails if no element found, or element style does not match expected value.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">style</span><span class="p">(</span><span class="s1">'#show-hide.hidden'</span><span class="p">,</span> <span class="s1">'display'</span><span class="p">,</span> <span class="s1">'none'</span><span class="p">);</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">style</span><span class="p">(</span><span class="s1">'#show-hide:not(.hidden)'</span><span class="p">,</span> <span class="s1">'display'</span><span class="p">,</span> <span class="s1">''</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="asserttextselection-expected-message">assert.text(selection, expected, message)</h4>

<p>Asserts that selected element(s) have the expected text content.  For example:</p>

<p>Fails if no element found that has that text content.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">text</span><span class="p">(</span><span class="s1">'title'</span><span class="p">,</span> <span class="s1">'My Awesome Page'</span><span class="p">);</span>
</code></pre></div></div>

<h4 id="asserturlurl-message">assert.url(url, message)</h4>

<p>Asserts the current page has the expected URL.</p>

<p>The expected URL can be one of:</p>

<ul>
  <li>The full URL as a string</li>
  <li>A regular expression</li>
  <li>A function, called with the URL and returns true if the assertion is true</li>
  <li>An <a href="http://nodejs.org/api/url.html#url_url_parse_urlstr_parsequerystring_slashesdenotehost">object</a>, in which case individual properties are matched against the URL</li>
</ul>

<p>For example:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">url</span><span class="p">(</span><span class="s1">'http://localhost/foo/bar'</span><span class="p">);</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">url</span><span class="p">(</span><span class="k">new</span> <span class="nb">RegExp</span><span class="p">(</span><span class="s1">'^http://localhost/foo/</span><span class="err">\\</span><span class="s1">w+$'</span><span class="p">));</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">url</span><span class="p">({</span> <span class="na">pathname</span><span class="p">:</span> <span class="s1">'/foo/bar'</span> <span class="p">});</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">url</span><span class="p">({</span> <span class="na">query</span><span class="p">:</span> <span class="p">{</span> <span class="na">name</span><span class="p">:</span> <span class="s1">'joedoe'</span> <span class="p">}</span> <span class="p">});</span>
</code></pre></div></div>

<h3 id="roll-your-own-assertions">Roll Your Own Assertions</h3>

<p>Not seeing an assertion you want?  You can add your own assertions to the
prototype of <code class="highlighter-rouge">Browser.Assert</code>.</p>

<p>For example:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="c1">// Asserts the browser has the expected number of open tabs.</span>
<span class="nx">Browser</span><span class="p">.</span><span class="nx">Assert</span><span class="p">.</span><span class="nx">prototype</span><span class="p">.</span><span class="nx">openTabs</span> <span class="o">=</span> <span class="kd">function</span><span class="p">(</span><span class="nx">expected</span><span class="p">,</span> <span class="nx">message</span><span class="p">)</span> <span class="p">{</span>
  <span class="nx">assert</span><span class="p">.</span><span class="nx">equal</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">browser</span><span class="p">.</span><span class="nx">tabs</span><span class="p">.</span><span class="nx">length</span><span class="p">,</span> <span class="nx">expected</span><span class="p">,</span> <span class="nx">message</span><span class="p">);</span>
<span class="p">};</span>
</code></pre></div></div>

<p>Or application specific:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="c1">// Asserts which links is highlighted in the navigation bar</span>
<span class="nx">Browser</span><span class="p">.</span><span class="nx">Assert</span><span class="p">.</span><span class="nx">navigationOn</span> <span class="o">=</span> <span class="kd">function</span><span class="p">(</span><span class="nx">linkText</span><span class="p">)</span> <span class="p">{</span>
  <span class="k">this</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">element</span><span class="p">(</span><span class="s1">'.navigation-bar'</span><span class="p">);</span>
  <span class="k">this</span><span class="p">.</span><span class="nx">assert</span><span class="p">.</span><span class="nx">text</span><span class="p">(</span><span class="s1">'.navigation-bar a.highlighted'</span><span class="p">,</span> <span class="nx">linkText</span><span class="p">);</span>
<span class="p">};</span>
</code></pre></div></div>

<h2 id="cookies">Cookies</h2>

<p>Are delicious.  Also, somewhat tricky to work with.   A browser will only send a
cookie to the server if it matches the request domain and path.</p>

<p>Most modern Web applications don’t care so much about the path and set all
cookies to the root path of the application (<code class="highlighter-rouge">/</code>), but do pay attention to the
domain.</p>

<p>Consider this code:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">setCookie</span><span class="p">({</span> <span class="na">name</span><span class="p">:</span> <span class="s1">'session'</span><span class="p">,</span> <span class="na">domain</span><span class="p">:</span> <span class="s1">'fourm.js.org'</span><span class="p">,</span> <span class="na">value</span><span class="p">:</span> <span class="s1">'delicious'</span> <span class="p">});</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">visit</span><span class="p">(</span><span class="s1">'http://fourm.js.org'</span><span class="p">,</span> <span class="kd">function</span><span class="p">()</span> <span class="p">{</span>
  <span class="kd">const</span> <span class="nx">value</span> <span class="o">=</span> <span class="nx">browser</span><span class="p">.</span><span class="nx">getCookie</span><span class="p">(</span><span class="s1">'session'</span><span class="p">);</span>
  <span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="s1">'Cookie'</span><span class="p">,</span> <span class="nx">value</span><span class="p">);</span>
<span class="p">});</span>
</code></pre></div></div>

<p>In order for the cookie to be set in this example, we need to specify the cookie
name, domain and path.  In this example we omit the path and choose the default
<code class="highlighter-rouge">/</code>.</p>

<p>To get the cookie in this example, we only need the cookie name, because at that
point the browser has an open document, and it can use the domain of that
document to find the right cookie.  We do need to specify a domain if we’re
interested in other cookies, e.g for a 3rd party widget.</p>

<p>There may be multiple cookies that match the same host, for example, cookies set
for <code class="highlighter-rouge">.fourm.js.org</code> and <code class="highlighter-rouge">www.fourm.js.org</code> will both match <code class="highlighter-rouge">www.fourm.js.org</code>, but
only the former will match <code class="highlighter-rouge">fourm.js.org</code>.  Likewise, cookies set for <code class="highlighter-rouge">/</code> and
<code class="highlighter-rouge">/foo</code> will both match a request for <code class="highlighter-rouge">/foo/bar</code>.</p>

<p><code class="highlighter-rouge">getCookie</code>, <code class="highlighter-rouge">setCookie</code> and <code class="highlighter-rouge">deleteCookie</code> always operate on a single cookie,
and they match the most specific one, starting with the cookies that have the
longest matching domain, followed by the cookie that has the longest matching
path.</p>

<p>If the first argument is a string, they look for a cookie with that name using
the hostname of the currently open page as the domain and <code class="highlighter-rouge">/</code> as the path.  To
be more specific, the first argument can be an object with the properties
<code class="highlighter-rouge">name</code>, <code class="highlighter-rouge">domain</code> and <code class="highlighter-rouge">path</code>.</p>

<p>The following are equivalent:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">getCookie</span><span class="p">(</span><span class="s1">'session'</span><span class="p">);</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">getCookie</span><span class="p">({</span> <span class="na">name</span><span class="p">:</span> <span class="s1">'session'</span><span class="p">,</span>
                    <span class="na">domain</span><span class="p">:</span> <span class="nx">browser</span><span class="p">.</span><span class="nx">location</span><span class="p">.</span><span class="nx">hostname</span><span class="p">,</span>
                    <span class="na">path</span><span class="p">:</span> <span class="nx">browser</span><span class="p">.</span><span class="nx">location</span><span class="p">.</span><span class="nx">pathname</span> <span class="p">});</span>
</code></pre></div></div>

<p><code class="highlighter-rouge">getCookie</code> take a second argument.  If false (or missing), it returns the
value of the cookie.  If true, it returns an object with all the cookie
properties: <code class="highlighter-rouge">name</code>, <code class="highlighter-rouge">value</code>, <code class="highlighter-rouge">domain</code>, <code class="highlighter-rouge">path</code>, <code class="highlighter-rouge">expires</code>, <code class="highlighter-rouge">httpOnly</code> and
<code class="highlighter-rouge">secure</code>.</p>

<h4 id="browsercookies">browser.cookies</h4>

<p>Returns an object holding all cookies used by this browser.</p>

<h4 id="browsercookiesdumpoutput">browser.cookies.dump(output?)</h4>

<p>Dumps all cookies to standard output, or the output stream.</p>

<h4 id="browserdeletecookieidentifier">browser.deleteCookie(identifier)</h4>

<p>Deletes a cookie matching the identifier.</p>

<p>The identifier is either the name of a cookie, or an object with the property
<code class="highlighter-rouge">name</code> and the optional properties <code class="highlighter-rouge">domain</code> and <code class="highlighter-rouge">path</code>.</p>

<h4 id="browserdeletecookies">browser.deleteCookies()</h4>

<p>Deletes all cookies.</p>

<h4 id="browsergetcookieidentifier-allproperties">browser.getCookie(identifier, allProperties?)</h4>

<p>Returns a cookie matching the identifier.</p>

<p>The identifier is either the name of a cookie, or an object with the property
<code class="highlighter-rouge">name</code> and the optional properties <code class="highlighter-rouge">domain</code> and <code class="highlighter-rouge">path</code>.</p>

<p>If <code class="highlighter-rouge">allProperties</code> is true, returns an object with all the cookie properties,
otherwise returns the cookie value.</p>

<h4 id="browsersetcookiename-value">browser.setCookie(name, value)</h4>

<p>Sets the value of a cookie based on its name.</p>

<h4 id="browsersetcookiecookie">browser.setCookie(cookie)</h4>

<p>Sets the value of a cookie based on the following properties:</p>

<ul>
  <li><code class="highlighter-rouge">domain</code> - Domain of the cookie (requires, defaults to hostname of currently
open page)</li>
  <li><code class="highlighter-rouge">expires</code> - When cookie it set to expire (<code class="highlighter-rouge">Date</code>, optional, defaults to
session)</li>
  <li><code class="highlighter-rouge">maxAge</code> - How long before cookie expires (in seconds, defaults to session)</li>
  <li><code class="highlighter-rouge">name</code> - Cookie name (required)</li>
  <li><code class="highlighter-rouge">path</code> - Path for the cookie (defaults to <code class="highlighter-rouge">/</code>)</li>
  <li><code class="highlighter-rouge">httpOnly</code> - True if HTTP-only (not accessible from client-side JavaScript,
defaults to false)</li>
  <li><code class="highlighter-rouge">secure</code> - True if secure (requires HTTPS, defaults to false)</li>
  <li><code class="highlighter-rouge">value</code> - Cookie value (required)</li>
</ul>

<h2 id="tabs">Tabs</h2>

<p>Just like your favorite Web browser, fourm manages multiple open windows as
tabs.  New browsers start without any open tabs.  As you visit the first page,
fourm will open a tab for it.</p>

<p>All operations against the <code class="highlighter-rouge">browser</code> object operate on the currently active tab
(window) and most of the time you only need to interact with that one tab.  You
can access it directly via <code class="highlighter-rouge">browser.window</code>.</p>

<p>Web pages can open additional tabs using the <code class="highlighter-rouge">window.open</code> method, or whenever a
link or form specifies a target (e.g. <code class="highlighter-rouge">target=_blank</code> or <code class="highlighter-rouge">target=window-name</code>).
You can also open additional tabs by calling <code class="highlighter-rouge">browser.open</code>.  To close the
currently active tab, close the window itself.</p>

<p>You can access all open tabs from <code class="highlighter-rouge">browser.tabs</code>.  This property is an
associative array, you can access each tab by its index number, and iterate over
all open tabs using functions like <code class="highlighter-rouge">forEach</code> and <code class="highlighter-rouge">map</code>.</p>

<p>If a window was opened with a name, you can also access it by its name.  Since
names may conflict with reserved properties/methods, you may need to use
<code class="highlighter-rouge">browser.tabs.find</code>.</p>

<p>The value of a tab is the currently active window.  That window changes when you
navigate forwards and backwards in history.  For example, if you visited the URL
‘/foo’ and then the URL ‘/bar’, the first tab (<code class="highlighter-rouge">browser.tabs[0]</code>) would be a
window with the document from ‘/bar’.  If you then navigate back in history, the
first tab would be the window with the document ‘/foo’.</p>

<p>The following operations are used for managing tabs:</p>

<h4 id="browsertabs-1">browser.tabs</h4>

<p>Returns an array of all open tabs.</p>

<h4 id="browsertabsnumber">browser.tabs[number]</h4>

<p>Returns the tab with that index number.</p>

<h4 id="browsertabsstring">browser.tabs[string]</h4>
<h4 id="browsertabsfindstring">browser.tabs.find(string)</h4>

<p>Returns the tab with that name.</p>

<h4 id="browsertabscloseall">browser.tabs.closeAll()</h4>

<p>Closes all tabs.</p>

<h4 id="browsertabscurrent">browser.tabs.current</h4>

<p>This is a read/write property.  It returns the currently active tab.</p>

<p>Can also be used to change the currently active tab.  You can set it to a
window (e.g. as currently returned from <code class="highlighter-rouge">browser.current</code>), a window name or the
tab index number.</p>

<h4 id="browsertabsdumpoutput">browser.tabs.dump(output?)</h4>

<p>Dump a list of all open tabs to standard output, or the output stream.</p>

<h4 id="browsertabsindex">browser.tabs.index</h4>

<p>Returns the index of the currently active tab.</p>

<h4 id="browsertabslength">browser.tabs.length</h4>

<p>Returns the number of currently opened tabs.</p>

<h4 id="browseropen-url">browser.open (url)</h4>

<p>Opens and returns a new tab.  Supported options are:</p>
<ul>
  <li><code class="highlighter-rouge">name</code> - Window name.</li>
  <li><code class="highlighter-rouge">url</code> - Load document from this URL.</li>
</ul>

<h4 id="browserwindow">browser.window</h4>

<p>Returns the currently active window, same as <code class="highlighter-rouge">browser.tabs.current.</code></p>

<h2 id="debugging">Debugging</h2>

<p>To see what your code is doing, you can use <code class="highlighter-rouge">console.log</code> and friends from both
client-side scripts and your test code.</p>

<p>To see everything fourm does (opening windows, loading URLs, firing events,
etc), set the environment variable <code class="highlighter-rouge">DEBUG=fourm</code>.  fourm uses the
<a href="https://github.com/visionmedia/debug">debug</a> module.  For example:</p>

<div class="language-bash highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nv">$ DEBUG</span><span class="o">=</span>fourm mocha
</code></pre></div></div>

<p>You can also turn debugging on from your code (e.g. a specific test you’re
trying to troubleshoot) by calling <code class="highlighter-rouge">browser.debug()</code>.</p>

<p>Some objects, like the browser, history, resources, tabs and windows also
include <code class="highlighter-rouge">dump</code> method that will dump the current state to the console, or an
output stream of your choice.  For example:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">dump</span><span class="p">();</span>
<span class="nx">browser</span><span class="p">.</span><span class="nx">dump</span><span class="p">(</span><span class="nx">process</span><span class="p">.</span><span class="nx">stderr</span><span class="p">);</span>
</code></pre></div></div>

<p>If you want to disable console output from scripts, set <code class="highlighter-rouge">browser.silent = true</code>
or once for all browser instances with <code class="highlighter-rouge">Browser.silent = true</code>.</p>

<h2 id="events">Events</h2>

<p>Each browser instance is an <code class="highlighter-rouge">EventEmitter</code>, and will emit a variety of events
you can listen to.</p>

<p>Some things you can do with events:</p>

<ul>
  <li>Trace what the browser is doing, e.g. log every page loaded, every DOM event
emitted, every timeout fired</li>
  <li>Wait for something to happen, e.g. form submitted, link clicked, input element
getting the focus</li>
  <li>Strip out code from HTML pages, e.g remove analytics code when running tests</li>
  <li>Add event listeners to the page before any JavaScript executes</li>
  <li>Mess with the browser, e.g. modify loaded resources, capture and change DOM
events</li>
</ul>

<h4 id="console-level-message">console (level, message)</h4>

<p>Emitted whenever a message is printed to the console (<code class="highlighter-rouge">console.log</code>,
<code class="highlighter-rouge">console.error</code>, <code class="highlighter-rouge">console.trace</code>, etc).</p>

<p>The first argument is the logging level, and the second argument is the message.</p>

<p>The logging levels are: <code class="highlighter-rouge">debug</code>, <code class="highlighter-rouge">error</code>, <code class="highlighter-rouge">info</code>, <code class="highlighter-rouge">log</code>, <code class="highlighter-rouge">trace</code> and <code class="highlighter-rouge">warn</code>.</p>

<h4 id="active-window">active (window)</h4>

<p>Emitted when this window becomes the active window.</p>

<h4 id="closed-window">closed (window)</h4>

<p>Emitted when this window is closed.</p>

<h4 id="done-">done ()</h4>

<p>Emitted when the event loop goes empty.</p>

<h4 id="error-error">error (error)</h4>

<p>Error when loading a resource, or evaluating JavaScript.</p>

<h4 id="evaluated-code-result-filename">evaluated (code, result, filename)</h4>

<p>Emitted after JavaScript code is evaluated.</p>

<p>The first argument is the JavaScript function or code (string).  The second
argument is the result.  The third argument is the filename.</p>

<h4 id="event-event-target">event (event, target)</h4>

<p>Emitted whenever a DOM event is fired on the target element, document or window.</p>

<h4 id="focus-element">focus (element)</h4>

<p>Emitted whenever an element receives the focus.</p>

<h4 id="idle-">idle ()</h4>

<p>Event loop is idle.</p>

<h4 id="inactive-window">inactive (window)</h4>

<p>Emitted when this window is no longer the active window.</p>

<h4 id="interval-function-interval">interval (function, interval)</h4>

<p>Emitted whenever an interval (<code class="highlighter-rouge">setInterval</code>) is fired.</p>

<p>The first argument is the function or code to evaluate, the second argument is
the interval in milliseconds.</p>

<h4 id="link-url-target">link (url, target)</h4>

<p>Emitted when a link is clicked.</p>

<p>The first argument is the URL of the new location, the second argument
identifies the target window (<code class="highlighter-rouge">_self</code>, <code class="highlighter-rouge">_blank</code>, window name, etc).</p>

<h4 id="loaded-document">loaded (document)</h4>

<p>Emitted when a document has been loaded into a window or frame.</p>

<p>This event is emitted after the HTML is parsed, and some scripts executed.</p>

<h4 id="loading-document">loading (document)</h4>

<p>Emitted when a document is about to be loaded into a window or frame.</p>

<p>This event is emitted when the document is still empty, before parsing any HTML.</p>

<h4 id="opened-window">opened (window)</h4>

<p>Emitted when a new window is opened.</p>

<h4 id="redirect-request-response">redirect (request, response)</h4>

<p>Emitted when following a redirect.</p>

<h4 id="request-request">request (request)</h4>

<p>Emitted before making a request to retrieve a resource.</p>

<p>The first argument is the request object.  See <a href="index.html#resources">Resources</a> for more
details.</p>

<h4 id="response-request-response">response (request, response)</h4>

<p>Emitted after receiving the response (excluding redirects).</p>

<p>The first argument is the request object, the second argument is the response
object.  See <a href="index.html#resources">Resources</a> for more details.</p>

<h4 id="serverevent-">serverEvent ()</h4>

<p>Browser received server initiated event (e.g. <code class="highlighter-rouge">EventSource</code> message).</p>

<h4 id="setinterval-function-interval">setInterval (function, interval)</h4>

<p>Event loop fired a <code class="highlighter-rouge">setInterval</code> event.</p>

<h4 id="settimeout-function-delay">setTimeout (function, delay)</h4>

<p>Event loop fired a <code class="highlighter-rouge">setTimeout</code> event.</p>

<h4 id="submit-url-target">submit (url, target)</h4>

<p>Emitted whenever a form is submitted.</p>

<p>The first argument is the URL of the new location, the second argument
identifies the target window (<code class="highlighter-rouge">_self</code>, <code class="highlighter-rouge">_blank</code>, window name, etc).</p>

<h4 id="timeout-function-delay">timeout (function, delay)</h4>

<p>Emitted whenever a timeout (<code class="highlighter-rouge">setTimeout</code>) is fired.</p>

<p>The first argument is the function or code to evaluate, the second argument is
the delay in milliseconds.</p>

<h4 id="xhr-event-url">xhr (event, url)</h4>

<p>Called for each XHR event (<code class="highlighter-rouge">progress</code>, <code class="highlighter-rouge">abort</code>, <code class="highlighter-rouge">readystatechange</code>, <code class="highlighter-rouge">loadend</code>,
etc).</p>

<h2 id="authentication">Authentication</h2>

<p>fourm supports HTTP basic access authentication. To provide the login credentials:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">on</span><span class="p">(</span><span class="s1">'authenticate'</span><span class="p">,</span> <span class="kd">function</span><span class="p">(</span><span class="nx">authentication</span><span class="p">)</span> <span class="p">{</span>
  <span class="nx">authentication</span><span class="p">.</span><span class="nx">username</span> <span class="o">=</span> <span class="s1">'myusername'</span><span class="p">;</span>
  <span class="nx">authentication</span><span class="p">.</span><span class="nx">password</span> <span class="o">=</span> <span class="s1">'mypassword'</span><span class="p">;</span>
<span class="p">});</span>

<span class="nx">browser</span><span class="p">.</span><span class="nx">visit</span><span class="p">(</span><span class="s1">'/mypage'</span><span class="p">);</span>
</code></pre></div></div>

<h2 id="resources">Resources</h2>

<p>fourm can retrieve with resources - HTML pages, scripts, XHR requests - over
HTTP, HTTPS and from the file system.</p>

<p>Most work involving resources is done behind the scenes, but there are few
notable features that you’ll want to know about. Specifically, if you need to do
any of the following:</p>

<ul>
  <li>Inspect the history of retrieved resources, useful for troubleshooting issues
related to resource loading</li>
  <li>Request resources directly, but have fourm handle cookies, authentication,
etc</li>
  <li>Implement new mechanism for retrieving resources, for example, add new
protocols or support new headers (see <a href="index.html#pipeline">Pipeline</a>)</li>
</ul>

<h3 id="the-resources-list">The Resources List</h3>

<p>Each browser provides access to the list of resources loaded by the currently
open window via <code class="highlighter-rouge">browser.resources</code>.  You can iterate over this list just like
any JavaScript array.</p>

<p>Each resource provides three properties:</p>

<ul>
  <li><code class="highlighter-rouge">request</code>   - The request object</li>
  <li><code class="highlighter-rouge">response</code>  - The resource object (if received)</li>
  <li><code class="highlighter-rouge">error</code>     - The error generated (no response)</li>
</ul>

<p>The request object is based on the <a href="https://fetch.spec.whatwg.org/#request-class">Fetch API Request
object</a>.</p>

<p>The response object is based on the <a href="https://fetch.spec.whatwg.org/#response-class">Fetch API Response
object</a>.  Note that the fetch API
has the property <code class="highlighter-rouge">status</code>, whereas Node HTTP module uses <code class="highlighter-rouge">statusCode</code>.</p>

<h4 id="browserfetchinput-init">browser.fetch(input, init)</h4>

<p>You can use the browser directly to make requests against external resources.
These requests will share the same cookies, authentication and other browser
settings (also pipeline).</p>

<p>The <code class="highlighter-rouge">fetch</code> method is based on the <a href="https://fetch.spec.whatwg.org/#fetch-method">Fetch
API</a>.</p>

<p>For example:</p>

<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code>browser.fetch(url)
  .then(function(response) {
    console.log('Status code:', response.status);
    if (response.status === 200)
      return response.text();
  })
  .then(function(text) {
    console.log('Document:', text);
  })
  .catch(function(error) {
    console.log('Network error');
  });
</code></pre></div></div>

<p>To access the response document body as a Node buffer, use the following:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">response</span><span class="p">.</span><span class="nx">arrayBuffer</span><span class="p">()</span>
  <span class="p">.</span><span class="nx">then</span><span class="p">(</span><span class="nx">Buffer</span><span class="p">)</span> <span class="c1">// arrayBuffer -&gt; Buffer</span>
  <span class="p">.</span><span class="nx">then</span><span class="p">(</span><span class="kd">function</span><span class="p">(</span><span class="nx">buffer</span><span class="p">)</span> <span class="p">{</span>
    <span class="nx">assert</span><span class="p">(</span> <span class="nx">Buffer</span><span class="p">.</span><span class="nx">isBuffer</span><span class="p">(</span><span class="nx">buffer</span><span class="p">)</span> <span class="p">);</span>
  <span class="p">});</span>
</code></pre></div></div>

<h4 id="resourcesdumpoutput">resources.dump(output?)</h4>

<p>Dumps the resources list to the output stream (defaults to standard output
stream).</p>

<h2 id="pipeline">Pipeline</h2>

<p>fourm uses a pipeline to operate on resources.  You can extend that pipeline
with your own set of handlers, for example, to support additional protocols,
content types, special handlers, etc.</p>

<p>The pipeline consists of a set of handlers.  There are two types of handlers:</p>

<p>Functions with two arguments deal with requests.  They are called with the
browser and request object.  They may modify the request object, and they may
either return null (pass control to the next handler) or return the Response
object, or return a promise that resolves to either outcome.</p>

<p>Functions with three arguments deal with responses.  They are called with the
browser, request and response objects.  They may modify the response object, and
must return a Response object, either the same as the argument or a new Response
object, either directly or through a promise.</p>

<p>To add a new handle to the end of the pipeline:</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">browser</span><span class="p">.</span><span class="nx">pipeline</span><span class="p">.</span><span class="nx">addHandler</span><span class="p">(</span><span class="kd">function</span><span class="p">(</span><span class="nx">browser</span><span class="p">,</span> <span class="nx">request</span><span class="p">)</span> <span class="p">{</span>
  <span class="c1">// Let's delay this request by 1/10th second</span>
  <span class="k">return</span> <span class="k">new</span> <span class="nb">Promise</span><span class="p">(</span><span class="kd">function</span><span class="p">(</span><span class="nx">resolve</span><span class="p">)</span> <span class="p">{</span>
    <span class="nx">setTimeout</span><span class="p">(</span><span class="nx">resolve</span><span class="p">,</span> <span class="mi">100</span><span class="p">);</span>
  <span class="p">});</span>
<span class="p">});</span>
</code></pre></div></div>

<p>You can add handlers to all browsers via <code class="highlighter-rouge">Pipeline.addHandler</code>.  These
handlers are automatically added to every new <code class="highlighter-rouge">browser.pipeline</code> instance.</p>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="nx">Pipeline</span><span class="p">.</span><span class="nx">addHandler</span><span class="p">(</span><span class="kd">function</span><span class="p">(</span><span class="nx">browser</span><span class="p">,</span> <span class="nx">request</span><span class="p">,</span> <span class="nx">response</span><span class="p">)</span> <span class="p">{</span>
  <span class="c1">// Log the response body</span>
  <span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="s1">'Response body: '</span> <span class="o">+</span> <span class="nx">response</span><span class="p">.</span><span class="nx">body</span><span class="p">);</span>
<span class="p">});</span>
</code></pre></div></div>



      </section>
      <footer>
        
        <p>This project is maintained by <a href="https://tetepay.github.io/fourm">fourm</a></p>
        
        <p><small>Hosted on GitHub Pages &mdash; Theme by <a href="https://tetepay.github.io/fourm">fourm</a></small></p>
      </footer>
    </div>
    <script src="assets/js/scale.fix.js"></script>


  
  </body>
</html>
