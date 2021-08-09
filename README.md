# README

We want to create a mini Touch & Sell Studio in Rails. Each Organization will have its own URL and will be able to build a tree structure of Nodes.

Organization represents a project/customer/application to build.

A Node is the basic element of the tree structure build for an Organization. There is one root node at the base of the tree structure, then nodes have a parent node and children nodes.

You must use the latest version of Rails 6.0.0 and Ruby.

This test is expected to take around 2 hours.

## Models

### Organization

* name

### Node

* name

## Expected routes

Organizations URLs should not have a prefix:

* `/new` Create a new organization
* `/OOOO` Show name of an organization, with a link to its root node. This URL is also used for destroy
* `/OOOO/edit` Edit an organization's name

Nodes should be under organizations

* `/OOOO/nodes/NNNN` Show a node content: name + children. This URL is also used for destroy
* `/OOOO/nodes/NNNN/edit` Edit a node's name
* `/OOOO/nodes/NNNN/new` Create a new node under this one

## Spec

* The root node of an organization must be browsable immediately after the creation of the organization
* The root node is the only node of an organization that does not have a parent
* The root node of an organization is not editable and its name is always the name of the organization
* Destroying a node should destroy all its descendants
* Destroying an organization should destroy all its nodes
* Updating a node should touch all its ancestors

## Quality Expectations

* clear navigation & location of actions
* clear naming conventions
* code as clear and minimalist as possible, using as many Rails features as possible to support future evolutions without a refactor
  * migrations
  * routes
  * models
  * controllers
* secure and prevent any data corruption or security issues
  * IMPORTANT: each organization must be strongly separated with no way to reveal nodes of another organization
* fast and to the point, caching if possible, no unnecessary SQL queries or method calls
* DRY, code reuse, patterns reusable in the future, even for a single method in this exercise
* clear & frequent commits with good messages
* complete the README section about explanations

NOT EXPECTED

* tests but you can create some if that allows you to speed up development
* complex UI, we only need basic HTML, no CSS or Javascript required
* multiple format requests, only HTML but think about it as a possible evolution

## Explanations

Please include a written report including all design decisions that you made and why you made them.

*I used XXXX because that allows me to...*

*I used YYYY because that will simplify the future for...*
