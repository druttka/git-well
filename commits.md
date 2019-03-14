# Commits

Back in 2011, I delivered a talk at TechMixer University called "Committed to Good Commits." I gave that talk again at CodeStock, and discussed it a few times with my teams over the years. While the talk had an expanded scope to cover branching strategies, continuous integration, dealing with conflicts, etc., there are a few points that apply discretely to the commits themselves.

> NOTE: The initial points here might seem to paint an idealistic picture of a perfect world. The final section of this page discusses how to balance these ideals against making progress in the real world.

## Atomicity

I strongly encourage atomic commits. That is, a commit should be a unit of work that accomplishes a single desired change. Why?

- If a revert is needed, you won't revert the proverbial baby with the bathwater
- If a bisect is used to determine a point of failure, it is clear what change introduced the failure
- This inherenty lends itself to more frequent commits, which I often compare to establishing checkpoints or saving your game before trying to [make it through the poison brambles](http://www.uhs-hints.com/uhsweb/hints/kq2/32.php)

One of the common concerns raised is whether this overcomplicates, clutters, or pollutes the graph. That's a fair question, and there are certainly tradeoffs. Depending on the branching strategy and team workflow, there are some [potential compromises](./atomic-compromises.md).

> TIP: If you realize you've done too much work at once and wish you had applied more granular commits, check out [`git add -p`](http://www.codefoster.com/addpatch/)! This allows you to stage *portions* of your working tree instead of entire files.

## Validation

Before commiting, I encourage taking a quick look to confirm what changes you're about to put into the repo. Does it build, lint, pass tests, etc.? Are you happy with the atomicity of this unit of work?

> TIP: Useful commands here are `git status`, `git diff`, and whatever you use to build and test. If you're staging only part of your changes, remember that builds and tests aren't aware of what you have or haven't staged, so they run against everything your working tree!

## Message

Give the commit a good, descriptive commit message. Let the first line be a summary level statement of what is changed. If you have a work item, include that on this line, as a lot of repository hosts and tooling will automatically associate the work item when you do.

After a blank line, go ahead and include more details around the hows, the whys, alternative approaches considered - whatever would help you and your team understand the work of this commit if they had to revisit it months from now. An example of what I'd ideally target as a through commit message would be [my commit to update Azure docs](https://github.com/druttka/azure-docs/commit/e2346ce48d01f2cad73ed214b32fadaf84bea710).

## It Depends, A.K.A. Let's Be Real

I'm not perfect on these points, and I don't expect anyone is. In many cases, there is no need to be perfect about this, and we should focus on delivering value.

"Initial commit" of a greenfield project, especially when it's a side effort or hack, isn't very descriptive. It's often not very atomic. There may be nothing to validate at such an early stage.

I don't always take things too seriously. [Why did I put an a tag in markdown?](https://github.com/druttka/scc-schedule/commit/afe2277d169b66c370f82cad598aae2e587e776a) is atomic, but the message is not very thorough. What I could have done better here, if it did matter:

```text
Change anchor tag to Matt's GitHub to markdown syntax
```

Looking at the commit in detail, I inadvertantly broke the link in this commit by setting the URL back to our own project instead of Matt's GitHub. It's clear that I wasn't doing a good job validating the commits here!

[Update sessions.json](https://github.com/druttka/scc-schedule/commit/771322b3c8f00c9c075be8b3dbf73bbbf8e1f317) would make me feel very guilty if it had been in a more serious or long-lived project. The commit message adds no value in terms of narrating the "story" of our project. I can always use `git show 771322b3c --stat` to see what files were touched in the commit.

```bash
 sessions.json | 256 +++++++++++++++++++++++++++++-----------------------------
 1 file changed, 128 insertions(+), 128 deletions(-)
 ```

It might have been better for me to say something like `Ensured that SessionUrl and SpeakerUrl are absolute.`

 > NOTE: We can also drop the `--stat` to get a full diff output for even more detail. But we shouldn't **require** our collaborators to do this just to read a high-level narrative history of our project. There are a bunch of "Update filex.y" commits in a row here, and there's no way to discern the intent of any of them from the commit messages.

Could [the most recent three commits](https://github.com/druttka/scc-schedule/commits/gh-pages) be any more vague?

`one more test`. Cool story, Dave! What was the test? Then I drill into the commit and it's adding a line of text to the README.md that literally reads "one more test," but WHY?! As I typed this, I honestly had no memory of what we were trying to do here.

After looking into the previous two commits, it becomes a bit more clear, but past me should not have required present me to drill into the commit details to figure that out. From the commit messages alone, present me thought our group had actually put **proper tests** around something. Present me is disappointed.

However, at the end of the day, a non-zero amount of people at Seattle Code Camp enjoyed a more navigable schedule on their phones that year. I am happy with what we delivered, and given that it was a [quick, dirty, hack](https://github.com/druttka/scc-schedule/commit/96ef5e4b27548d250cfa57fda4e147daa4632b9b), the commit quality doesn't matter.