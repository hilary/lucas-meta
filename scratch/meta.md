# Mission

Critique and improve code challenge

## Goals

* Reveal working profile of developer:
  * Who are they? (Ask Lucas what he has in mind)
  * Strengths?
  * Weaknesses?
  * Level?

* Don't burden developer. Respect their time.

* Communicate:
  * who we are as a company
  * what our technology is about

* _I would add_
  * be fun
  * screen out problem developers (this could fall under 'working profile')
  * improve acceptance rates

## About current version

The current version has a lot of text not to add complexity and/or difficulty,
but to add clarity and be helpful. (Has the current version gotten longer over
time in response to questions from folks who have taken the challenge?) The
amount of text isn't necessarily a problem.

## Quotes from the job description

...headless components of our music API, including:

* Crawling Discogs, Wikipedia, Facebook, Twitter, Instagram, Musicbrainz, etc
* Downloading, categorizing, reformatting huge batches of artist images
* Creating public web APIs
* Searching our data store using Elastic Search and/or Postgres
* Calling various social media and music APIs
* Architectural improvements for speed and stability at scale

...heterogenous bag of tools including Scala, Node, and Hadoop, as well as
Rails. We're trying to move all that into Ruby, and preferably Rails.

If you live in the shell, you’re probably already familiar with the tools on
our workbench, e.g. git, REST, JSON, Mongo, Postgres, Jenkins, nginx, gems, and
AWS.

## How are we doing at our goals?

* I think the rewritten version (or several additional revisions of the rewritten
  version) is respectful of the developer's time. It feels like it's sized right,
  although I'll need to complete it at some point to be sure. The code challenge
  needs to be large enough to be interesting but small enough to be reasonable.
  The fact that some people will consider themselves too sought-after to do the
  challenge is a positive in my mind, not a negative. If we use the tool to
  hire devs, they should be eager to do it.

* While I rather like the mistake in some ways, we need to consider the burden
  on the developer. It significantly increases the burden either on them or on
  us, because it requires that: they progress without feedback, or they wait to
  sync up, or we make a major effort to be responsive. None of those sound like
  fun, at least for true team players. Stress happens without us introducing
  more, lol. Although... it does induce a dialog. Argh. Way to be decisive,
  Hilary. Perhaps we could be really explicit about saying 'talk to us'? The
  non-talky folks still won't talk.

* I like the ambiguity w/re provider ordering. I'd want to see how the dev
  solves the problem. Asking for an answer is acceptable, of course. It's
  generally not the best solution in such a situation, because ambiquity is
  often a reflection of an incomplete thought. For example, what about ties?

* The challenge certainly exposes the dev to our tech. By the onsite, they've
  explored the company, the API, etc. We've improved the chances of meaningful
  interactions during the onsites. I'd rather have fewer onsites with better
  outcomes. Onsites are expensive.

* We can learn something about their [12factor](#http://12factor.net) habits
  from how they manage their API key, although Rails 4 does protect folks more
  than previous versions did.

* Removing the explicit info about tests tells us a huge amount about how
  they understand agile. (Jenkins! Yay, Jenkins!)

* Doing the app in stages tells us a huge amount about their skill level
  w/re object-oriented design in Ruby (yay, Sandi Metz). I'll be able to be
  more explicit about that once I've been through it all the way once, and
  we can tweak the steps to expose what we want to expose.
