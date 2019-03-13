# Commits

Back in 2011 (?), I delivered a talk at TechMixer University called "Committed to Good Commits." I gave that talk again at CodeStock, and discussed it a few times with my teams over the years. For me, there are a few things to keep in mind when creating commits.

## Atomicity

I strongly encourage atomic commits. That is, a commit should be a unit of work that accomplishes a single desired change. Why?

- If a revert is needed, you won't revert the proverbial baby with the bathwater
- If a bisect is used to determine a point of failure, it is clear what change introduced the failure
- This encourages "frequent" commits, which I often compare to establishing checkpoints or saving your game trying to [make it through the poison brambles](http://www.uhs-hints.com/uhsweb/hints/kq2/32.php)

One of the common concerns raised is whether this overcomplicates, clutters, or pollutes the graph. That's a fair question, and there are certainly tradeoffs. Depending on the branching strategy, there are some [potential compromises](./atomic-compromises.md).

> TIP: If you realize you've done too much work at once and wish you had applied more granular commits, check out `git add -p`! This allows you to stage *portions* of your working tree instead of entire files.

## Validation

Before commiting, I encourage taking a quick look to confirm what changes you're about to put into the repo. Does it build, lint, pass tests, etc.? Are you happy with the atomicity of this unit of work?

> TIP: Useful commands here are `git status`, `git diff`, and your test runner. Remember that tests are running against everything your working tree, which may or may not be the changes you've staged for the commit!

## Message

Give the commit a good, descriptive commit message. Let the first line be a summary level statement of what is changed. If you have a work item, include that on this line, as a lot of repository hosts and tooling will automatically associate the work item when you do.

After a blank line, go ahead and include more details around the hows, the whys, alternative approaches considered - whatever would help you and your team understand the work of this commit if they had to revisit it months from now.