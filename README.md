# Journal

## 12:30pm, Saturday, April 25

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

## 1:09pm

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


## 2:00pm

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

## 4:00pm (give or take)

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
