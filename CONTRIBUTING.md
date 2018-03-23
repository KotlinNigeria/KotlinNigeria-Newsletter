# Contributing to *KotWek*

*Contributions are welcome and encouraged!*

First and foremost, please review and abide by [our code of conduct](https://github.com/dennisotugo/KotlinNigeria-Newsletter/blob/master/CODE_OF_CONDUCT.md).

You should have a good understanding of how [Jekyll](http://jekyllrb.com) and [GitHub-Pages](https://pages.github.com) work — or be willing to learn. :smile: We are happy to help you with any questions, just ask!

**Suggestions:** Have something you want to share in the newsletter? Please find [the current issue notes](vissues?q=is%3Aissue+is%3Aopen+label%3A%22current+issue%22) and add a comment. Or you can [open an issue][issueLink] or [submit a pull request][prLink] to the [current draft](https://github.com/dennisotugo/KotlinNigeria-Newsletter/tree/master/_drafts) with a link and description.

**Fixes:** Spelling, grammar, or code. Please [open an issue][issueLink] or [submit a pull request][prLink]!

## ⚙️ Setup and process

1. Add yourself to [`_data/authors.yml`](https://github.com/dennisotugo/KotlinNigeria-Newsletter/blob/master/_data/authors.yml), if you haven't already. Please provide:
    - A username to reference for the site
    - Your name
    - GitHub username
    - Twitter username
1. Run the [`new_draft.sh`](https://github.com/dennisotugo/KotlinNigeria-Newsletter/blob/master/new_draft.sh) script to generate an issue template in `_drafts/`. See the example below.
1. Open an issue on GitHub. Set the title to the newsletter issue number and date. 
**Example:** `[100] Issue #100 - Jan 04, 2018`
1. Assign it to yourself. 
1. Add the [`current issue` and `full issue notes`](https://github.com/dennisotugo/KotlinNigeria-Newsletter/issues?utf8=✓&q=is%3Aissue+label%3A%22current+issue%22+label%3A%22full+issue+notes%22+) labels.  
1. We use this throughout the week to collect notes and make it easy for external contributors to contribute content. We also use this issue to collaborate with the others and troubleshoot any problems that come up.
1. Write the issue in `_drafts/` throughout the week. We recommend writing a little each day to make it easier. 
1. For style and content, see the guide below. Also, follow the example set by previous issues.
1. **For code snippets, use jekyll highlight blocks:** 
```jekyll
{% highlight kotlin %} 

// kotlin code here

{% endhighlight %}
```

> 💡 **Note:** See the handy tips below!

### Generating a draft

Example:

```bash
# usage: ./new_draft.sh <DATE (yyyy-MM-dd)> <ISSUE #> <AUTHOR>

$ ./new_draft.sh 2016-04-21 19 jsq  

# creates _drafts/2016-04-21-issue-19.md 
```

### Preview the site locally, with drafts

```bash
$ bundle exec jekyll build --future --drafts 

# -- or --

$ bundle exec jekyll serve --future --drafts --watch
```

## 📝 Writing style guide

We encourage all writes to use their own voice and express their own personality in their writing. This is what makes a great issue.

*Some guidelines on writing style:*

* All content must align with [Our Standards](https://github.com/SwiftWeekly/swiftweekly.github.io/blob/master/CODE_OF_CONDUCT.md#our-standards), outlined in the Code of Conduct. Language must be welcoming, inclusive, respectful, etc.

* Maintain an overall positive tone. We want to avoid being overly negative. However, this *does not* mean we should not be critical. Constructive criticism is valid and should be presented in non-aggressive way.

* Use simple past tense. This is simpler and easier to read, flows better, and is particularly easier for ESL readers. **Example:**
    * Do this: *"Chris Lattner wrote a manifesto."* ✅
    * Not this: *"A manifesto was written by Chris Lattner."* ❌

* Avoid jargon and abbreviations when possible. 
    * **Example:** use *pull request* rather than *PR*
    * **Example:** write *for example* rather than *e.g.*

* Avoid contractions if possible. Again, this is easier to read, especially for ESL readers. 
    * **Example:** use *do not* rather than *don't*.

* For the *"Commits and pull requests"* section use the format: `PERSON did ACTION`. 
    * **Example:** *"Chris Lattner opened a pull request for a prototype of async/await."*

* For "Proposals in review" use the format: `SE-NNNN: TITLE by AUTHOR is under review`.
    * **Example:** [SE-0185](https://github.com/apple/swift-evolution/blob/master/proposals/0185-synthesize-equatable-hashable.md): *Synthesizing Equatable and Hashable conformance* by Tony Allevato is [under review](https://lists.swift.org/pipermail/swift-evolution-announce/2017-August/000397.html).

* For "Accepted proposals", "Rejected Proposals", etc. use the format: `SE-NNNN: TITLE was STATUS`.
    * **Example:** [SE-0150](https://github.com/apple/swift-evolution/blob/master/proposals/0150-package-manager-branch-support.md): Package Manager Support for branches [was accepted](https://lists.swift.org/pipermail/swift-evolution-announce/2017-February/000315.html).

## 🕵️‍♀️ Evaluating ~~mailing list~~ [Swift Forum](https://swift.org/community/#forums) content

Not all ~~mailing list~~ forum discussions are important and valuable enough to be listed in the newsletter. There can be a lot of noise and bikeshedding that simply is not relevant to readers — or ideas are not solid enough. Try to avoid these and focus on "big picture" ideas and discussions pertinent to current or future proposals.

Some good indications on whether or not a discussion is worth including:
* There is a lot of activity and replies.
* The Core Team or broader Swift team has responded positively.
* The Core Team or broader Swift team is highly engaged in the discussion.

> 💡 **Note:** This does not mean that discussions without these characteristics are not worth mentioning. These are simply a few guidelines.

# 📰 Publishing an issue

> 💡 **Note:** We publish *every other Thursday*.

New issues should be pushed to `master` **before noon** Pacific Time, preferably around 10 or 11 a.m. if possible. Pushing early allows us to catch and fix any last minute errors. If there are any problems, contact Baro.

1. When ready to publish, move the `.md` file from `_drafts/` to the `_posts/` directory.
2. Run `jekyll build` on your local copy to preview.
3. Make sure everything looks good. :ok_hand:
4. Submit a [pull request][prLink] or push to `master`. :tada:

### ~~Emails~~

~~Emails are automatically sent via Mailchimp's [RSS-to-Email](https://mailchimp.com/features/rss-to-email/) feature. **Publishing too late (*at or after* noon PST) will prevent emails from being sent.** If emails fail to send on Thursday at noon PST, Mailchimp will retry on Friday at noon PST.~~

### Tweets

Tweets from [@KotlinNigeria](https://twitter.com/kotlinNigeria) are automated via [IFTTT](https://ifttt.com). 

## 🎢 Continuous integration

We use [travis-ci](https://travis-ci.org/SwiftWeekly/swiftweekly.github.io), [danger](http://danger.systems), and [proselint](http://proselint.com) (via [danger-prose](https://github.com/dbgrandi/danger-prose)). This ensures:

- We're always pushing valid markdown and `jekyll` can build the site.
- We write elegant prose — no grammar/spelling mistakes, and no offensive or unwelcoming language. See the [`Dangerfile`](https://github.com/dennisotugo/KotlinNigeria-Newsletter/blob/master/Dangerfile) for more details.

## 💡Tips

- Watch all of the main [Kotlin repositories](https://github.com/kotlin).
- Follow the prominent [contributors](https://github.com/orgs/jetbrains/people) on GitHub and Twitter.
- When in doubt, refer to previous issues for examples.
- Keep a draft running throughout the week, add a little bit of content each day.

[issueLink]:https://github.com/Sdennisotugo/KotlinNigeria-Newsletter/issues/new
[prLink]:https://github.com/dennisotugo/KotlinNigeria-Newsletter/compare
