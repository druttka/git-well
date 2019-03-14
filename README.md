# How I Git

People that I work with will frequently suggest to me that I write something about my git workflow(s). Historically, I have hesitated to do this.

One primary reason is that "it depends." Given the nature of the project, the team culture, non-functional requirements like audits and compliance, and a general feeling that there are (over) 9000 ways to do anything with git, a **discussion** is typically the most effective way forward.

Another is that over the past eight years, I've come to my understanding of git through hands-on experience combined with leveraging what others already shared. As to the former, anyone on my teams knows that I'm **always** happy to pay it forward and share my git experience, but again, it's usually more effective if it's hands-on or a collaborative discussion. As to the latter, I have no desire to take the work that others have put in and pretend that it's my own.

To mitigate these hesitations, I'm going to attempt to frame my thoughts here as if they were one of those discussions with my team. I'll also start out by redirecting you to the resources which I commonly recommend. [Issues](https://github.com/druttka/how-i-git/issues) will be enabled, so that can be an effective way for anyone to ask questions or bring up additional discussion points.

Through it all, it bears repeating that "it depends." Please take all of this not as a "do or do not" prescriptive screed, but as a guide for evaluating what works best for you and for your teams.

## My Git Learning Path (Prerequisites)

When I help someone through an "interesting" situation with git, there are a few concepts that very frequently come up. Sometimes, after covering these concepts, people come to their own solution or answer their own question. When we do have continued discussions, it's much easier because we have a shared context.

Given that experience, before discussing concrete workflows I feel that it's important to establish that same shared context. Before continuing, please take a look at my thoughts on [an effective git learning path](./my-git-learning-path.md).

## My Git Workflows

I'll be filling these out as soon as time allows, but I wanted to establish a roadmap. In the long term, I also hope to organize the raw thoughts into a decision matrix to highlight which workflow I typically go to when given some set of variables (number of collaborators, type of project, whether it accepts community PRs, team culture, team familiarity with git, etc.).

> For most of these topics, the short answer will be "it depends." Expect a **discussion of whens, whys, and tradeoffs.**

- What about the [command line versus graphical tools](./cli-vs-graphical.md)?
- What about making [commits](./commits.md)?
- What about branching strategies like:
    - partying directly on the mainline (aka trunk based)?
    - [gitflow](https://nvie.com/posts/a-successful-git-branching-model/)?
    - [GitHub flow](https://guides.github.com/introduction/flow/)?
- What about fetch versus pull?
- Can you just tell me the sequence of commands you use every time, assuming nothing has gone wrong?
- What about forks?
- Why is my new PR for one new commit also including a large number of old commits?
- What about rebase versus merge?
- What about squashing?

## License

I'm putting this under the CC0-1.0 license. The full text is in the [LICENSE](./LICENSE) file. This is put into more human terms at [choose a license](https://choosealicense.com/licenses/cc0-1.0/) and at [Creative Commons](https://creativecommons.org/publicdomain/zero/1.0/). In short, my intent is that this is public domain.