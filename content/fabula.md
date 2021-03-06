Ivan Sutherland says, "It's not an idea until you write it down." With that in
mind, here is a series of thoughts I have recently been thinking.

---

How do you feel when you walk through a library? Perhaps you feel relaxed by
the silence, comforted by the presence of books at your side. Perhaps you feel
awed by the pages that surround you, or inspired by the wonderful tales you
know they contain.

I feel all these emotions, but I also feel a little despair. A library has
thousands and thousands of books. Surely I will never make it through even a
small fraction of them --- no matter how hard I try, even if I read constantly
for years, there will always be books remaining, books I might have loved and
cherished if only I had decided to read them. It is more than despair: the
state of mind is perhaps best described as preemptive regret.

Such is life. But as I walk between the bookshelves at my local library, it
nevertheless seems natural --- even prudent --- to wonder: is there any end in
sight? Will writers ever run out of stories to tell? Of distinctive plots, of
clever endings, of engaging characters? Surely there are a finite number of
words, a finite number of ways to meaningfully combine those words, and thus
eventually one must reach a limit on the number of stories those words can
tell. What happens if we tell them all, if we saturate our own Library of
Babel? What then?

In 2004, Christopher Booker published a book called *The Seven Basic Plots: Why
We Tell Stories*. He argued that all stories fall into one of seven categories,
such as "Rags to Riches" (*Cinderella* and *Jane Eyre*) or "Overcoming the
Monster" (*Beowulf* and *Harry Potter*). Though harshly received by critics,
Booker's idea serves well to introduce the thesis of this blog post: that it is
not the story, but rather its *telling*, that matters.

What is the difference between a story and its telling? For that, let us borrow
a pair of words from the Russian formalists, who began the modern tradition of
narratology. The Russian formalists made a distinction between the *fabula* and
the *syuzhet* of a story. The fabula is the actual story as it would be written
in a history textbook: the real sequence of events, in their chronological
order, the --- to appeal to Kant --- the noumenal, *das-Ding-an-sich* view of a
tale. The syuzhet is the way the story is told: the organization of scenes, the
development of characters, the surprise ending, the --- to once more appeal to
Kant --- the phenomenal. The former is a *story*, the latter is a *plot*. If
fabula is the theory of differential calculus, syuzhet is a well-delivered
lecture on the subject. If fabula is a prism, syuzhet is a rainbow. If fabula
is a galaxy, syuzhet is a telescope.

The thesis of this post is therefore that to the art of storytelling, the
syuzhet matters much more than the fabula. Booker's seven basic plots attempt
to restrict the possible fabulae, but an infinitude of syuzhets leave us with
generations of thought-provoking literature. The *Odyssey* and *The Wizard of
Oz* both narrate Booker's "Voyage and Return" Fabula, but the syzhets are
different enough for the stories to have vastly different meanings and impacts
on our minds. The stories teach us different lessons, make us laugh and cry in
different places, and make us empathize with different characters.
Nevertheless, they both follow a very predictable order of events. It seems,
therefore, that the work of a writer is to create syuzhet, not fabula.

And so, as computer scientists, we must ask ourselves, "can we automate the
creation of fabula?"

---

I want to first clarify that I am not talking about creating some sort of Great
Automatic Grammatizer. And I certainly am not trying to reduce literature to a
series of theorems. Rather, I want to use computation as a lens to explore
stories in a new way. The purpose, therefore, is not to generate a novel
automatically --- that sounds horrifying --- but rather to generate the
*framework* of a novel automatically. A writer can then focus on expressing
herself without worrying about crafting a compelling storyline through which to
do so. After all, a writer with a fascinating character, setting, or parable in
mind still requires a medium for those elements to occupy. A readymade fabula
provides a starting point, and above all, assurance that the story is going
*somewhere*. A fabula protects you from the prospect of a contrived
deus-ex-machina ending.

Perhaps the best work on the computational generation of fabula comes from
Chris Martens' thesis, in which she reveals [a wonderful
connection](https://www.cs.cmu.edu/~cmartens/thesis/) between stories and
Girard's linear logic. (For a taste of linear logic, a good reference paper is
[this](http://homepages.inf.ed.ac.uk/wadler/papers/lineartaste/lineartaste-revised.pdf)
set of lecture notes by Philip Wadler.) Briefly, Martens' work allows you to
create rules by which propositions change over time. These rules are much like
algebraic manipulations; indeed, in a way, her idea equates *stories* with
*proofs*. Ceptre, a proof-of-concept implementation of this work, lets you
create rich interactive narratives as well as complete stories.

(Further related work is covered by
[this](https://graphics.tudelft.nl/Publications-new/2016/KB16/Survey.pdf)
survey paper. Of particular interest is the incredibly-well-named [Narrative
Intelligence Lab](https://nil.cs.uno.edu/publications/) at the University of
New Orleans, which publishes papers like [*A Computational Model of Plan-Based
Narrative Conflict at the Fabula
Level*](https://nil.cs.uno.edu/publications/papers/ware2014conflict.pdf).)

But while Martens' work creates a *logical* story effectively (which is very
useful for interactive fiction), what we seek here is a *powerful* story. We
want stories that make us *feel* rather than *think*. For that, we need new
tools.

Having said that, I must now admit that I have little to say about what such
tools might actually *be*. I have been thinking about it for many months now,
and have yet to make any progress.

Some ideas stand out. Surely, the heart of fabula is conflict, and in
particular, conflict of morals. Hamlet conflicts between revenge and
self-preservation; Brutus between friendship and freedom; Juliet between love
and family. Perhaps there is a way to take an arbitrary pair of values, and, by
some nondeterministic process, construct a situation that forces a character to
choose between them. Rather than Ceptre's forward-chaining proof strategy, we
might instead appeal to a form of resolution-refutation to generate interesting
situations.

Another part of fabula must be the asymmetry of information: there is
distinction between the knowledge of each character (not to mention the reader
and even the narrator). The function of information asymmetry is usually
obvious. Consider, for example the classic murder mystery: Poirot's stories
rely on the murderer knowing what Poirot doesn't, of Poirot knowing what the
murderer doesn't, of Hastings --- a proxy for the reader --- not knowing much
in general. Yet information asymmetry is present in far more than just murder
mysteries. Even *Romeo and Juliet* relies on a sequence of misunderstandings at
the end.

Fate, too, has its role in narrative, as do its counterparts, intention and
motive. And what of irony? Does irony belong in fabula or syuzhet? *The Gift of
the Magi* relies on irony for its fabula, whereas Shakespeare uses irony to
enrich the syuzhet of *Hamlet*.

Searching for the fundamental building blocks of effective fabula --- the
*narremes* that build up the *narratives* --- is an exercise left for you to
ponder along with me. As you read novels and short stories over the next few
weeks, I invite you to try to distill the fabula from the syuzhet, and then to
decide what exactly makes the fabula compelling. As with all fascinating
questions, the answers may not be to our liking --- or they may be too complex
for us to mold into tractable generalizations --- or they may be disappointing
in their simplicity.

But then, what's an adventure without a little danger?
