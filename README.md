These files are the Tiny Speck patch to support rendering of timing graphs in the <a 
href="http://code.flickr.com/blog/2008/10/27/counting-timing/">Flickr StatsD style</a> in Graphite.

Copy these files into <code>graphite/webapp/graphite/render/</code> and restart your web server for them to take effect.
The graphs use stats following the <a href="https://github.com/tinyspeck/statsd">Tiny Speck StatsD</a> pattern:

    stats.timers.foo (key set, not an actual stat)
    stats.timers.foo.min
    stats.timers.foo.percent_10
    stats.timers.foo.percent_50
    stats.timers.foo.percent_90
    stats.timers.foo.max

To render a timer, add this to the render URL:

    &timer=stats.timers.foo
    &timer=stats.timers.bar.www*   # supports wildcard paths (will sum them)
    &timer=^stats.timers.baz       # for graphs where bigger means better

Examples
--------

<img src="http://www.iamcal.com/images/fps_sample.png" />

(Need some better ones!)
