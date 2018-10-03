# Nestable2RTL
New pickup of RTL Nestable!

basic and ltr version : https://github.com/RamonSmit/Nestable2 - Something changed to use RTL.

Drag & drop hierarchical list with mouse and touch compatibility (jQuery / Zepto plugin)

<h2><a id="user-content-usage" class="anchor" aria-hidden="true" href="#usage"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Usage</h2>
<p>Write your nested HTML lists like so:</p>
<div class="highlight highlight-text-html-basic"><pre>&lt;<span class="pl-ent">div</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd<span class="pl-pds">"</span></span>&gt;
    &lt;<span class="pl-ent">ol</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-list<span class="pl-pds">"</span></span>&gt;
        &lt;<span class="pl-ent">li</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-item<span class="pl-pds">"</span></span> <span class="pl-e">data-id</span>=<span class="pl-s"><span class="pl-pds">"</span>1<span class="pl-pds">"</span></span>&gt;
            &lt;<span class="pl-ent">div</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-handle<span class="pl-pds">"</span></span>&gt;Item 1&lt;/<span class="pl-ent">div</span>&gt;
        &lt;/<span class="pl-ent">li</span>&gt;
        &lt;<span class="pl-ent">li</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-item<span class="pl-pds">"</span></span> <span class="pl-e">data-id</span>=<span class="pl-s"><span class="pl-pds">"</span>2<span class="pl-pds">"</span></span>&gt;
            &lt;<span class="pl-ent">div</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-handle<span class="pl-pds">"</span></span>&gt;Item 2&lt;/<span class="pl-ent">div</span>&gt;
        &lt;/<span class="pl-ent">li</span>&gt;
        &lt;<span class="pl-ent">li</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-item<span class="pl-pds">"</span></span> <span class="pl-e">data-id</span>=<span class="pl-s"><span class="pl-pds">"</span>3<span class="pl-pds">"</span></span>&gt;
            &lt;<span class="pl-ent">div</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-handle<span class="pl-pds">"</span></span>&gt;Item 3&lt;/<span class="pl-ent">div</span>&gt;
            &lt;<span class="pl-ent">ol</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-list<span class="pl-pds">"</span></span>&gt;
                &lt;<span class="pl-ent">li</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-item<span class="pl-pds">"</span></span> <span class="pl-e">data-id</span>=<span class="pl-s"><span class="pl-pds">"</span>4<span class="pl-pds">"</span></span>&gt;
                    &lt;<span class="pl-ent">div</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-handle<span class="pl-pds">"</span></span>&gt;Item 4&lt;/<span class="pl-ent">div</span>&gt;
                &lt;/<span class="pl-ent">li</span>&gt;
                &lt;<span class="pl-ent">li</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-item<span class="pl-pds">"</span></span> <span class="pl-e">data-id</span>=<span class="pl-s"><span class="pl-pds">"</span>5<span class="pl-pds">"</span></span> <span class="pl-e">data-foo</span>=<span class="pl-s"><span class="pl-pds">"</span>bar<span class="pl-pds">"</span></span>&gt;
                    &lt;<span class="pl-ent">div</span> <span class="pl-e">class</span>=<span class="pl-s"><span class="pl-pds">"</span>dd-nodrag<span class="pl-pds">"</span></span>&gt;Item 5&lt;/<span class="pl-ent">div</span>&gt;
                &lt;/<span class="pl-ent">li</span>&gt;
            &lt;/<span class="pl-ent">ol</span>&gt;
        &lt;/<span class="pl-ent">li</span>&gt;
    &lt;/<span class="pl-ent">ol</span>&gt;
&lt;/<span class="pl-ent">div</span>&gt;</pre></div>
<p>Then activate with jQuery like so:</p>
<div class="highlight highlight-source-js"><pre><span class="pl-en">$</span>(<span class="pl-s"><span class="pl-pds">'</span>.dd<span class="pl-pds">'</span></span>).<span class="pl-en">nestable</span>({ <span class="pl-c"><span class="pl-c">/*</span> config options <span class="pl-c">*/</span></span> });</pre></div>

more detail : https://github.com/RamonSmit/Nestable2#usage
