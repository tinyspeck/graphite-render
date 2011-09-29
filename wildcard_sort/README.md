Target Wildcard Sorting
=======================

If you have a target such as <code>stats.*.load_avg</code>, where the wildcard is for hostnames, 
it makes sense for the results to be sorted, using a natural sort (so that www2 comes before 
www10). This simple patch does just that.

Using natural sort code found here: 
http://code.activestate.com/recipes/285264-natural-string-sorting/
