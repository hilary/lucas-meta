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


