# Journal

* [Saturday, April 25](#saturday-april-25)
  * [Intro](#intro)
  * [Initial pass through meta challenge](#initial-pass-through-meta-challenge)
  * [Initial revision of code challenge](#initial-revision-of-code-challenge)
  * [Comments after quick call with Lucas](#comments-after-quick-call-with-lucas)
  * [Initial design of additional steps in code challenge](#initial-design-of-additional-steps-in-code-challenge)
  * [A skeleton for the app](#a-skeleton-for-the-app)
  * [Both repos on Github](#both-repos-on-Github)
* [Sunday, April 26](#sunday-april-26)
  * [Making the journal more useful](#making-the-journal-more-useful)
  * [Thoughts about the challenge](#thoughts-about-the-challenge)
  * [Strategy for tackling the challenge](#strategy-for-tackling-the-challenge)

_I worked on the challenge over a weekend as I had time. I dated the intial
entry in the journal each time I came back to the challenge. The dates are
as much a habit from ethnomethodology as anything else._

## Saturday, April 25

### Intro
_12:30pm_

On call is happy, cats are fed, life is dealt with, sitting down to look at the
challenge.

I'm going to keep running notes as I go, to help me return to a less informed
mindset w/re the challenge.

I set up a workspace:

    README.md
    src/
      meta_challenge.txt (Lucas's email)
      challenge.txt      (text of the challenge)
    scratch/    (to think aloud about each of the above)
      meta.md
      challenge.md

I decided to track changes in git, because what else would I use?  Created the
repo locally and commited.

### Initial pass through meta challenge
_1pm_

Took a pass through the meta challenge, reached out to Lucas, moving on to the
challenge itself. I've read through it once before.

Interesting gut-level reaction on opening the challenge again: "Wow, that's a
lot of text." Hmmmm... Not good.

I woke up this morning thinking that the challenge as currently written is well
designed to screen for whether a candidate asks questions. While that's an
important behavior to screen for, I find it easy to sort out in the on-site, so
don't find it necessary to put in the code challenge.

We might be able to help with the wall-o-text effect simply by restructuring.
I'm going to see what I can do as I take an initial pass through.

I'm pulling in some detail for the meta challenge from the job description to
guide reading the challenge.

### Initial revision of code challenge
_2pm_

Rewrote the first paragraph, started on the second, did some digging around the
OpenAura developer site.

Note: http://openaura.com/apps/new could be a bit confusing. Under the heading
"REQUEST AN API KEY" it says "In order to obtain an API key, you must log in or
create an OpenAura account." The 'create an OpenAura account' link just brings
you back to the same page. Hmmmmm....

Got an API key

Love the visual design. Nice and clean.

Taylor Swift. Too funny.

I like the API documentation interface!

'The standard particles call' - What's the 'standard particles call'? The only
thing it looks like it could be would be /v1/particles/artists/{id}.

    curl -XGET 'http://api.openaura.com/v1/particles/artists/47?limit=10&id_type=oa:artist_id&api_key=API_KEY'

Yup. Gets what I would expect.

The id prefilled into /v1/particles/sources/{id} yields an error! Grab a valid
source id, fill in, yup, /v1/particles/sources/{id} would be the endpoint to
pull "an artist's particles by source" once we have the set of an artist's
particles. There's an error in the challenge. Is it deliberate? I have mixed
feelings about including deliberate errors.

Through an initial revision of code challenge. Going to commit, get a snack, see
if I can reach Lucas to resolve whether my understanding is flawed or whether
there is an error in the challenge.

### Comments after quick call with Lucas
_4pm_

Talked to Lucas, yup it's an error. Will explore thinking behind error when we
talk again. Took a break, back to work.

Some quick notes.

I wouldn't include suggestions about tests in the challenge at all. Testing is simply
too important a habit and skill set to prompt around to give away. It's the first
thing folks who haven't internalized it pitch overboard when under pressure or simply
when not supervised closely. So I took all the info about testing out of the challenge.

I also removed the comment about Heroku out of the challenge. I'd rather the dev face
the need to include a README so the person evaluating has to run the app locally. If
I can't install and run your app following your instructions, that tells me something.

Testing and documentation are skills, sure, but before they are skills they are
ways of thinking. We can teach the skill. We can't teach the way of
thinking. It's too easy for a candidate for whom testing and writing is like
pulling teeth to skate through an interview as someone who looks fun to be
around, projects confidence, and prepped for the interview just right. Then
you've got a developer that has a vested interest in changing your definition of
done to meet their approach.

Btw, I'm extrapolating OpenAura's values from: the inclusion of tests in the
challenge, the comment that the amount of text wasn't inherently a bad thing,
the quality of the API docs, ..., what else? But I feel reasonably confident about
my extrapolation :)

Ok, I'm going to build an initial version of the app while waiting for Lucas to
get back to me. I think I'll do that in a separate repo. Not sure why. Because.
That's why.

### Initial design of additional steps in code challenge

When I went back to start on the app, I reread the additional info I had separated out
and it sort of separated itself out into an initial set of additional steps. Not sure
it will work out, but it has a similar design test feel to it now. Intrigued to see
how it plays out.

### A skeleton for the app

Don't forget about the beacon! Use beacon gif (prepend api.openaura.com/v1)

    rails new openaura_cc --skip-bundle --skip-active-record

Clean out the cruft (mailers, jobs, etc.) Basic pieces in place, configure api
key in secrets. Putting api key in environment in development, too, as it's just
as easy as specifying production every time I run the thing...

Funny, this app is an odd little beast. Because I wouldn't write it (a single
page app) in Ruby, lol, it isn't immediately clear to me what to drop into
it. That's cool.

(To Lucas: just so you know, I'm a fan of chruby and ruby-install, even in dev
environments. I like my environments to be as consistent as possible.)

### Both repos on Github
_7pm_

Realized I had actually dropped my API key in this repo at one point as I had
not intended to put it on github. Heh. Never, never, never. Anyway. Did a quick
reconstruction of the repo (preserving history) without the API key
(thankyouverymuch). Ended up with a time shift but the order is the same. Ah well.
Never, never, never.

Will also upload prepped skeleton of app so as to be ready to work on it next
break I get.

## Sunday, April 26

### Making the journal more useful
_8am_

Spent some time with this journal. (Didn't change any of the text, of course.)
I'd already starting using semantically titled subsections yesterday. Today
I headed each section semantically, after the main topic of the section, and
moved the start time to metadata after the heading. Grouped entries by day
and added a table of contents. Much better.

### Thoughts about the challenge

I'll clean these notes up and add them to `meta.md` later.

I really like the design of the challenge.

* It's as much a pure Ruby challenge as a Rails challenge, in that you can't
  fall back on generators, etc., to complete it.

* As it is written now, it presents a real temptation to start with
  implementation, in the API calls, rather than interaction. We'd like to
  capture as much of that process as we can. Perhaps we should say 'commit early,
  commit often'? (Added instructions to that effect to the revised challenge.)

* When I think of 'level', I'm looking for depth of understanding as much as
  anything. The ability to recognize patterns and use them (including
  anti-patterns).

### Strategy for tackling the challenge

I'm going to start with interaction :)

A high-level plan of attack

1. do a quick mockup of the views
1. write and implement one e2e test at a time, mocking in the responses using
   real data from developer.openaura.com/docs
1. add in the logic to do the actual calls


