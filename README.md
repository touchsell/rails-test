# README

We want to create a mini Touch & Sell Studio in Rails. We can create a unique URL for each organization, then each organization can build its own tree structure.

You must use Rails 6.0.0 and Ruby 2.6.3.

## Models

### Organization

* name

### Node

* name
* association to 1 organization
* association to other nodes using parent/children (tree structure)

## Expected routes

Organizations URLs should not have a prefix:

* `/new` Create a new organization
* `/OOOO` Show name of an organization, with a link to its root node. This URL is also used for destroy
* `/OOOO/edit` Edit an organization's name

Nodes should be under organizations

* `/OOOO/nodes/NNNN` Show a node content: name + children. This URL is also used for destroy
* `/OOOO/nodes/NNNN/edit` Edit a node's name
* `/OOOO/nodes/NNNN/new` Create a new node under this one
* we should also be able to destroy a node

## Spec

* The root node of an organization must be browsable immediately after its creation
* The root node of an organization is not editable and its name is always the name of the organization
* Destroying a node should destroy all its descendants
* Destroying an organization should destroy all its nodes
* Updating a node should touch all its ancestors
* To improve code readbility, the Node associations for the tree must be named `children` and `parent`

## Quality Expectations

* clear navigation & location of actions
* clear naming conventions
* code as clear and minimalist as possible, using as many Rails features as possible to support future evolutions without a refactor
  * migrations
  * routes
  * models
  * controllers
* secure and prevent any data corruption or security issues
  * each organization should be separated with no way to leak data between them
* fast and to the point, no unnecessary SQL queries or method calls
* DRY, code reuse, patterns reusable in the future, even for a single method in this exercise
* clear & frequent commits with good messages
* complete the README section about explanations

NOT EXPECTED

* tests but you can create some if that allows you to speed up development
* complex UI, basic HTML only, no CSS or Javascript required
* multiple format requests, only HTML but think about it as a possible evolution

## Explanations

Here you will write a report including all design decisions that you made and why you made them.
Add arguments to your answer.

*I used XXXX because that allows me to...*
*I used YYYY because that will simplify the future for...*
