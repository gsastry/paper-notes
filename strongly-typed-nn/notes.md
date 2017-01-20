# Title: Strongly-Typed Recurrent Neural Networks #
# Authors: David Balduzzi, Muhammad Ghifry #

# Notes


# Summary
The authors introduce a some guiding principles to the design of
RNN architectures and apply them, and test them.

It's a little odd that they say that "adding meters to seconds" is
a type constraint from physics: that seems like a straightforward
type error in type theory.

# Intro

Not sure what this part means "Whereas
feedforward nets learn to approximate functions, recurrent
nets learn to approximate programs – suggesting lessons
from language design are relevant to RNN design", seems a little
imprecise, programs are computable functions no?

# Representations as types

Let a `type` = a vector space with an orthogonal basis. Then each
layer (node?) in a neural network learns a type (a representation).

A type is equipped with some operations and a fairly straightforward
encoding to a list of vectors ($d$ vectors in a type of dimension $d$).

But why?


** TODO - come back to this, getting distracted by applying NNs to 
program synthesis


