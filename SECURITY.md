# How to report

To report a security vulnerability to pandas, please go to https://tidelift.com/security and see the instructions there.

# What to report

pandas is fundamentally a data analysis library. We're most interested in reports where pandas claims to provide a security boundary but fails to meet it in some way.

We occasionally recieve vulnerability reports for a few areas that we're unlikely to consider a vulnerability, which we've documented below. If you're unsure whether to report something then please do report it and we'll discuss it.

## Data Input

Several data input methods include the option to use [pickle](https://docs.python.org/3/library/pickle.html) to load arbitrary Python objects, which can execute arbitrary Python code. pandas does not provide any security on top of pickle, and so likely won't consider reports involving pickle a security vulnerability.

## Data Output

pandas includes the ability to output a DataFrame to various formats, including formats like HTML. pandas doesn't attempt to sanitize the HTML such that it's safe to serve either trusted or untrusted input, and so likely won't consider reports of serving pandas-generated HTML a security vulnerability.

## eval / query

pandas includes some methods to evaluate expressions in the context of a DataFrame using various engines (numexpr, Python eval). pandas doesn't provide any security on top of those libraries, and so likely won't consider reports involving eval or query on untrusted input a security vulnerability.
