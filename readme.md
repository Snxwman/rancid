# rancid

Rancid was an attempt to build a couple of things on top of EWW.

* A widget library.
* A framework for building widgets in a configurable and adaptable manner.
* A vaguely tailwind-like styling syntax/library that would allow users to swap visual structure and theme with ease.

None of these goals were truly accomplished, nor a path to satisfactory completion identified. 

It eventually became apparent that EWW simply isn't built in a way that makes this possible without major feature additions and architectural reworks.
Yuck is an insufficiently complete language for the purpose of writing flexible and reusable code. However, the lisp syntax is wonderful for writing config-as-code.
If yuck was swapped out for a complete lisp a number of problems and hacky workarounds would disappear.

Development here has ceased with no plans to restart unless major changes to EWW are made.

EWW is a good widget solution. The above is not to say EWW is bad, just that it is not feasible to 'build on top of' at the current time.
