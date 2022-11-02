# 🌲 [Scrapbook](https://scrapbook.hackclub.com/): Into The Redwoods 🌲

![Redwoods, generated by Stable Diffusion.](https://user-images.githubusercontent.com/39828164/192213895-e6331b24-7ffb-45ef-98f4-9380d604318f.png)

Scrapbook was originally developed in 2020 for the Summer of Making. Since then, it has received bug fixes & minor feature updates. However, there hasn't been major full time development on the project. We're currently exploring what a Scrapbook v2 looks like and have drafted up a these notes on what a second version of Scrapbook looks like (after a general spring cleaning of the codebase):

_**1. Club leaders have a tool that they can use to post regularly about their club through and keep an archive of club projects.**_

**Why (for leaders)?** Club leaders feel like they’re creating something, gives them a method of sharing their club with HQ + wider community + internet & gives them a marketing tool within their school.

**Why (for club members)?** Accountability system, gives them a sharable profile of work done in their Hack Club & to feel like they’re contributing to something bigger than their school club.

Similar to [blair.hackclub.com/scrapbook](https://blair.hackclub.com/scrapbook) and [memphishack.com/projects.html](https://memphishack.com/projects.html).

_**2. Hackathon organisers have a tool that their participants can ship on as the hackathon progresses.**_

**Why (for hackathon organisers)?** Gives them a project sharing system, gives them a way of sharing their hackathon’s outcome and takes the work off them for infrastructure whilst making it still feel like their own.

**Why (for attendees)?** A clear end to the hackathon (the ship!), a way to explore other’s projects easily and to feel like they’re contributing to something bigger than their local hackathon.

Similar to [scrapbook.assemble.hackclub.com](https://scrapbook.assemble.hackclub.com) and [scrapbook.lelandhacks.com](https://scrapbook.lelandhacks.com/).

_**3. Scrapbook meets Clubs and Hackathons where they are.**_

The existing Scrapbook requires Slack for content. We've learned that Hack Clubs and Hackathons use a variety of other communication tools - mostly commonly Discord and Web. So, we're building support for these.

_**4. Scrapbook continues to support Hack Clubbers on Slack in sharing everything they’re learning on a daily basis.**_

Read on for more context on Scrapbook's current role in the Hack Club community.

### Contribute to Scrapbook's Rebuilding

If you're interested in helping make Scrapbook special, we'd love to have your help!

Here's how to get involved:

1. Join the [`#scrapbook-dev`](https://hackclub.slack.com/archives/C0C78SG9L/p1662043963377279) channel in the Hack Club Slack. Look around for any features needing implementing. Can't see anything? Drop a message in the channel, we'll find something!
2. Clone this Github repository, spin up a local PostgreSQL database (check out [this guide](https://www.prisma.io/dataguide/postgresql/setting-up-a-local-postgresql-database)!) and ask `@sampoder` (on Slack) for the project's `.env`.
3. Run `yarn` and then `yarn rw dev` to start your developer server!

Need help or want to share some thoughts? Get in touch through Slack in [`#scrapbook-dev`](https://hackclub.slack.com/archives/C0C78SG9L/p1662043963377279), [GitHub Issues](https://github.com/hackclub/scrapbook/issues) or [email](mailto:sam@hackclub.com).

## All About Scrapbook

Scrapbook helps you **share the things you're working on every day!** As a [Hack Clubber](https://hackclub.com/), you are always learning and building things. Scrapbook allows you to share updates on the things you're doing with the rest of the Hack Club community, and keeps you motivated by recording each day you contribute, tallying that up onto a streak shown on your profile.

Scrapbook was made by the Hack Club community because many of us have found that **showing up every day** has been key to our success in learning. Even if we didn’t make something big or impressive, showing up consistently and making _something_ was key.

## How do I join?

Your Scrapbook is automatically generated for you when you make your first Scrapbook post. In order to post, you'll need to [join the Hack Club Slack](https://hackclub.com/slack). Once you've completed the onboarding flow in Slack and have access to all of the channels, join the `#scrapbook` channel. From here, Scrapbook posts are automatically generated for you when you post a message in the `#scrapbook` channel.

A post requires just two things: a description and an image. Your image can be dragged straight into Slack and Scrapbook will take care of the rest. [An example message](https://hackclub.slack.com/archives/C01504DCLVD/p1646030307450419) into Slack might look like:

```
learned Express generator today - now back to a ton of (organized) files
```

![Example Scrapbook post image](https://cloud-f8by3gcpv-hack-club-bot.vercel.app/0screenshot_2022-02-27_223754.png)

_Example pulled from [audreyolafz's scrapbook](https://scrapbook.hackclub.com/audreyolafz)_

## Scrappy (the Slack Bot)

Scrappy, our handy dandy [Slack bot](https://github.com/hackclub/scrappy), not only handles the automatic generation of things, but provides some helpful commands as well. These commands are also documented in our Slack if you send the message `/scrappy` in any channel.

- `/scrappy-togglestreaks`: toggles your streak count on/off in your status
- `/scrappy-togglestreaks all`: opts out of streaks completely
- `/scrappy-open`: opens your scrapbook (or another user's if you specify a username)
- `/scrappy-setcss`: adds a custom CSS file to your scrapbook profile. [Check out this cool example](https://scrapbook.hackclub.com/msw)!
- `/scrappy-setdomain`: links a custom domain to your scrapbook profile, e.g. [scrapbook.maggieliu.dev](https://scrapbook.maggieliu.dev/)
- `/scrappy-setusername`: change your profile username
- `/scrappy-setaudio`: links an audio file to your Scrapbook. [See an example here](https://scrapbook.hackclub.com/matthew)!
- `/scrappy-setwebhook`: create a Scrappy Webhook we will make a blank fetch request to this URL every time you post
- `/scrappy-webring`: adds or removes someone to your webring
- _Remove_ a post: delete the Slack message and Scrappy will automatically update for you
- _Edit_ a post: edit the Slack message and it will automatically update for you
- _Post_ to the `#scrapbook` channel or add an existing Slack message to Scrapbook by reacting to it with the `:scrappy:` emoji (Note: If it isn't working, make sure Scrappy is added to the channel by mentioning `@scrappy`)

## Custom domains

To put your profile on your own domain, run `/scrappy setdomain <domain>` in Slack, giving your website’s hostname (e.g. [`scrapbook.maggieliu.dev`](https://scrapbook.maggieliu.dev)). Then, add a `CNAME` record on your DNS provider, pointed to `cname.vercel-dns.com`. If you’re curious how this works, it’s [open source right here](http://github.com/hackclub/summer-domains).

## CSS customization

To customize the CSS on your profile page, run `/scrappy setcss <link>` in Slack, giving a link to a CSS file or a [GitHub Gist](https://gist.github.com). [Here’s the default CSS](https://scrapbook.hackclub.com/themes/default.css), for your overwriting pleasure.

Want to preview your CSS before adding it to your profile? Check out [@jasonappah](https://github.com/jasonappah)’s [Scrapbook Customizer](https://scrapbook.hackclub.com/customizer).

If you are a beginner at coding and need a more in depth guide on how to work with CSS, check out [@sampoder](https://github.com/sampoder)’s workshop on the topic, this covers different useful areas like CSS variables, fonts and making custom animations. You can access it from [here](https://workshops.hackclub.com/scrapbook_css/).

### Colors & fonts

If you’d like to change the page-wide fonts or colors, you can change yours with [CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables). Here’s the values the site uses by default:

```css
:root {
  --colors-pink: #ff62dc;
  --colors-orange: #ff5b00;
  --colors-yellow: #f7ff00;
  --colors-green: #28ff00;
  --colors-cyan: #00ffff;
  --colors-blue: #00a4ff;
  --colors-purple: #c210ff;

  --colors-darker: #151613;
  --colors-dark: #20201d;
  --colors-darkless: #2b2b27;
  --colors-black: #1d201d;
  --colors-slate: #3b413a;
  --colors-muted: #777f76;
  --colors-smoke: #d5d8d5;
  --colors-snow: #f5f5f4;
  --colors-white: #ffffff;

  --fonts-body: 'Baloo 2', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, sans-serif;
  --fonts-display: 'Shrikhand', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, sans-serif;
  --fonts-mono: 'SF Mono', 'Roboto Mono', Menlo, Consolas, monospace;
}
```

Some “relative” colors use these colors for various components:

- `--colors-background` – page background color
- `--colors-text` – page text color
- `--colors-elevated` – “elevated” content, like the posts
- `--colors-sunken` – “sunken” content
- `--colors-progress` – the color of the progress bar

Our dark mode is powered by [`prefers-color-scheme: dark`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme).

## Website widget

Want to showcase your streak on your personal website? We’ve created a small widget that you can put on your website with two lines of code. It shows up in the bottom right corner. Just replace `username` with your Scrappy username. Here’s the code snippet:

```js
<script src="https://summer.hackclub.com/scrapbookwidget.js"></script>
<script>displayScrapbookUsername('username')</script>
```

If you have a custom domain, you can optionally link the scrapbook widget to it! Do it like this:

```js
<script src="https://summer.hackclub.com/scrapbookwidget.js"></script>
<script>displayScrapbookUsername('username', 'https://scrapbook.example.com')</script>
```

## RSS feed

Want to get an RSS feed of your Scrapbook posts? Just append `.rss` to the end of your Scrapbook profile's URL, like so: https://scrapbook.hackclub.com/(username).rss

## macOS app

Hack Clubbers using a Mac can post directly from their menu bar using Scrapple, an app built by [@LinusSkucas](https://github.com/LinusSkucas)! From the menu bar, type in the update, select the attachments for the post and send it off into the interweb…

You can [download the app here](https://github.com/LinusSkucas/Scrapple), and check out the [open source code here](https://github.com/LinusSkucas/Scrapple).

To install using Homebrew Cask:

```
brew tap LinusSkucas/homebrew-taps
brew install --cask scrapple
```

## Public API

This site exposes a public JSON API powered by [Next.js API routes](https://nextjs.org/docs/api-routes/introduction). The live site runs entirely on this API.

- [`/api/posts`](https://scrapbook.hackclub.com/api/posts) – Get all posts (used on the homepage)
- [`/api/users`](https://scrapbook.hackclub.com/api/users) – Get all users
- [`/api/users/:username`](https://scrapbook.hackclub.com/api/users/zrl) – Get a specific user’s profile + posts
- [`/api/users/:username/mentions`](https://scrapbook.hackclub.com/api/users/sampoder/mentions) – Get a specific user’s mentions
- [`/api/r/:emoji`](https://scrapbook.hackclub.com/api/r/hardware) – Get all posts tagged with a specific emoji
- [`/:username.png`](https://scrapbook.hackclub.com/sampoder.png) – Get a user's avatar as an image URL

## Contributing

Contributions are encouraged and welcome! There are two GitHub repositories that contain code for Scrapbook: the [Scrapbook website](https://github.com/hackclub/scrapbook#contributing) and [Scrappy the Slack bot](https://github.com/hackclub/scrappy#contributing).

Development chatter happens in the [#scrapbook-dev](https://app.slack.com/client/T0266FRGM/C035D6S6TFW) channel in the [Hack Club Slack](https://hackclub.com/slack/).

## Running Locally

1. Clone this repository
   - `git clone https://github.com/hackclub/scrapbook.git && cd scrapbook`
1. Install dependencies
   - `yarn`
1. Send a message mentioning `@creds` in [Hack Club's Slack](https://hackclub.com/slack/) asking for the `.env` file
1. Start server
   - `yarn dev`
1. View your server
   - `open http://localhost:3000/`

Those with access to HQ's Vercel account can also generate their own `.env` file:

1. Install Vercel's CLI (if you haven't already)
   - `yarn global add vercel`
1. Link Vercel to your account for deployment
   - `vercel`
1. Pull environment variables from Vercel
   - `vercel pull`

## How does it all work underneath?

Behind the scenes, the site runs on [Next.js](https://nextjs.org), React.js, & [SWR](https://swr.now.sh) for data fetching. All pages are [static-rendered](https://nextjs.org/docs/basic-features/data-fetching#getstaticprops-static-generation), hosted on [Vercel](https://vercel.com). Videos are hosted by [Mux](https://mux.com). The custom domains use a [Vercel serverless function](https://github.com/hackclub/summer-domains). The [Slack integration](https://github.com/hackclub/scrappy) runs on [Express.js](https://expressjs.com), hosted on [Heroku](https://heroku.com). All the data is stored in a [PostgreSQL](https://www.postgresql.org) database, fetched using [Prisma](https://prisma.io).

## The Origin of Scrapbook

Scrapbook was originally built in a week while preparing for the 2020 [Summer of Making](https://summer.hackclub.com/). To support makers, Hack Club distributed $50,000 in free electronics to 28 different countries. Scrapbook was made to help Hack Clubbers showcase the things they were doing during this event, but grew into a tool that the community uses every single day.

---

Hack Club, 2022. MIT License.