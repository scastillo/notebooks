# Notebooks

This is a playgrouond of some interesting problems I use to play with and share, think of it as a conversation starter arounds some beers or something. Don't take anything here seriously.

## Quantum

### bernstein-vazirani

Implementation: [bernstein-vazirani.ipynb](https://github.com/scastillo/notebooks/quantum/bernstein-vazirani.ipynb)

Suppose we are given a classical Boolean function, f : {0, 1}n → {0, 1}. Such a function is guaranteed to be of the form, 
fs(x) = <hs, xi>. Here, s is an unknown vector, which we shall call a hidden string; and <·, ·> is the usual vector dot product. 

Let us also suppose that we are given a black-box implementation of this function, and are tasked with
identifying the hidden string s with the least possible number of queries to the black box.

Since each classical query to this function produces just 1 bit of information, and since an arbitrary hidden string s
has n-bits of information, the classical query complexity is seen to be n. Even with bounded error, there is no way
that this classical complexity can be brought down, as can be seen using slightly more rigorous information theoretic
arguments.

Bernstein and Vazirani [10] built upon the earlier work of Deutsch and Jozsa [32] in theoretically exploring quantum
query complexity. Their contribution to the field was a quantum algorithm for the hidden string problem, which has a
non-recursive quantum query complexity of just 1. This constitutes a polynomial O(n) query-complexity separation
between classical and quantum computation. 

They also discovered a less widely known recursive hidden-string query algorithm, which shows a O(n log n) separation 
between classical and quantum query-complexities. These developments preceded the more famous results of Shor and Grover, 
and kindled a lot of early academic interest in the inherent power of quantum computers.

One thing to note with respect to the Bernstein-Vazirani (BV) quantum hidden-string query algorithm is that the
black-box function fs(·) can be very complex to implement using reversible quantum gates—for an n-bit hidden string,
the number of simple gates needed to implement fs(·) scales typically as O(4n). Since the black box is a step in the
algorithm, its serial execution time could in the worst-case even scale exponentially as O(4n). The real breakthrough
of this quantum algorithm lies in speeding up the query complexity and not the execution time per se.
