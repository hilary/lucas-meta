# OpenAura Code Challenge

There is no time limit but the goal is not to spend days of your time on this,
so please reach out at anytime for any questions you might have or if you get
stuck at any point.

## About the OpenAura API

The OpenAura API serves media and content related to _artists_.

* A piece of media relating to an artist is a _particle_.
* Every particle comes from a _provider_, e.g., Facebook.
* The intersection of an artist and a provider is a _source_, e.g., an artist's
  band page on Facebook.

Read more about the api and sign up for an api key at
http://developer.openaura.com/.

The standard particles endpoint (/v1/particles/artists/{id}) returns particles
in a round robin manner with equal weighting by provider, ordered by date. For
example, if an artist only had three providers A, B and C, the particle order
would look like: A1, B1, C1, A2, B2, C2, A3 … etc. This approach results in an
equal distribution of recent particles per provider and a nice variation in the
returned set. In English, you don’t just get a list of Facebook particles where
an artist also has Twitter, Instagram, Youtube, etc.

## Step 1

Build a single page RAILS app that recreates the standard particle response
round robin structure without using /v1/particles/artists/{id}. You could use
/v1/source/artists/{id} to pull an artist’s sources, then
/v1/particles/sources/{id} to pull the particles for those sources.  Provider
ordering is determined by the date of the most recent particle, per artist
source.

The output and all user interactions on the page can by very simple - we
are NOT looking for the prettiest page and are more concerned with basic
user interactions and particle ordering. The particle listing only needs
to show

* provider name
* particle date
* particle id

per particle. Showing the particle media on the page is not required. You can
limit the particle list to the first 100 particles (more is okay).

How to setup the app and which gems to use are up to you, but we ask that
the OpenAura API requests are done on the Ruby server side, not on the
client side.

Build your project in source control, Github or something similar. When you
have finished this step, tag the commit as step1, push, then continue.

## This stuff should come in additional steps...

The app must allow a user to choose between multiple artists and
to choose the size of the round robin slice.  Artist choice can simply be a
preset list of artists (2+) or an interface to a search, but search is not
required; if using preset list, please ensure the artist is relatively popular
with sufficient content ( openaura.com a good place to check).  The slice
determines how many particles per provider should appear in a row.  In the three
provider example above, slice = 1.  With slice = 2, it would look like: A1, A2,
B1, B2, C1, C2, A3, A4, B3, B4, C3, C4 … etc.  You can bound the slice value
from 1 to 5.

