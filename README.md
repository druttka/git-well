# How I Git

People that I work with will frequently suggest to me that I write something about my git workflow(s). Historically, I have hesitated to do this for a few reasons.

First, "it depends." Given the nature of the project, the team culture, non-functional requirements like audits and compliance, and the [OVER 9000!](https://www.youtube.com/watch?v=SiMHTK15Pik) ways to do anything with git, a **discussion** is typically the most effective way forward.

Second, I have nothing novel to say here.

Third, I'm always learning! What I said to my team three years ago is very different from what I'll say today.

To mitigate these hesitations, I'm going to attempt to frame my thoughts here as if they were one of those  discussions with my team. I'll also start out by redirecting you to the resources which I commonly recommend. By delivering this as a repo, I hope to continue adding and updating as necessary. Issues will be enabled, so that can be an effective way for anyone to ask questions or bring up additional discussion points.

> Through it all, keep in mind that this is only me sharing what has worked for me over the years. You should evaluate what works best for you and for your teams.

## My Git Learning Path

When I help someone through an "interesting" situation with git, there are a few concepts that very frequently come up. Sometimes, after covering these concepts, people don't need me anymore. When we do have continued discussions, it's much easier because we have a shared context.

Before discussing concrete workflows, I feel that it's important to establish that same shared context. There is [a plethora of existing git resources](https://github.com/jongio/gitawesome), but people have expressed to me that it can be difficult to determine which are the best investments.

I believe that the following path will have the most critical impact for how effectively you use git. Specific resources will follow.

- Understand that git is a graph
- Understand that branches and tags are refs (pointers)
- Understand the relationships between working, staging, and the repository
- Understand the relationship between local repositories and the zero-to-many remotes

### Git Happens

I cannot overstate how much impact Jessica Kerr's [Git Happens](https://www.youtube.com/watch?v=Dv8I_kfrFWw) had on my understanding and thought processes around git. I had been dabbling with git (my teams were still using a lot of TFS and SVN), and this talk helped me build a proper mental model of what was happening.

To this day, when people ask me how I learned to think about git the way that I do, this is where I send them. In about an hour, you'll gain critical understanding of the four points above.

Go watch it! There's also a [companion website](http://jessitron.github.io/git-happens/).

### How To Teach Git

If you prefer text over videos (or why not both?!), [How To Teach Git](https://rachelcarmena.github.io/2018/12/12/how-to-teach-git.html) is a fantastic resource that was recently shared with me. The illustrations here can really help things click.

### Git is a Graph

This is also covered in the Git Happens talk, but in my opinion it's worth emphasizing again.

On Windows, I typically tell a person I'm helping to pop up `gitk` and visualize the graph. After we talk through it, understanding and visualizing the graph is an "aha!" moment.

I like [Git is a Directed Acyclic Graph and What the Heck Does That Mean?](https://medium.com/girl-writes-code/git-is-a-directed-acyclic-graph-and-what-the-heck-does-that-mean-b6c8dec65059) as an additional reference on this topic. There's also the [Graphs and Git](http://think-like-a-git.net/sections/graphs-and-git.html) section of [Think Like (a) Git](http://think-like-a-git.net/).

### Cheatsheets And FAQs

Please feel free to use these. In my **personal opinion**, they're best used as **reminders** after you grok everything covered in the references above.

To quote [Rachel](https://rachelcarmena.github.io/2018/12/12/how-to-teach-git.html),

> They didn’t know the reason why those steps. They only knew that they should follow them in order not to get into trouble.

I would echo this, and I would add that in my experience, following the steps without knowing why can make a bad git situation *worse*. I've seen this when a person chooses the steps they *believe* apply to the current situation because the error message looks *similar enough* (or even identical), but they truly needed something very different.

My take on it: First, critically reason over the graph, the staging area, your working directory, etc. to determine **what** you want to achieve. Then, use the cheatsheets to remember specific commands, args, etc. to accomplish that result.

All of this said, I do very much enjoy [ohshitgit](http://ohshitgit.com/), and I hope you do too!

## My Git Workflows

I'll be filling out these pages over the next several days, but I wanted to establish an outline of things to come.

1. [One contributor, one branch](./my-git-workflows/one-dev-one-branch) 
1. One contributor, multiple branches
1. Multiple contributors, one branch
1. Multiple contributors, multiple *individual* branches
1. Multiple contributors, multiple *shared* branches
1. Merge or Rebase? Squash?!