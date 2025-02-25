Title: This Week in Rust 401
Number: 401
Date: 2021-07-28
Category: This Week in Rust

Hello and welcome to another issue of *This Week in Rust*!
[Rust](http://rust-lang.org) is a programming language empowering everyone to build reliable and efficient software.
This is a weekly summary of its progress and community.
Want something mentioned? Tweet us at [@ThisWeekInRust](https://twitter.com/ThisWeekInRust) or [send us a pull request](https://github.com/rust-lang/this-week-in-rust).
Want to get involved? [We love contributions](https://github.com/rust-lang/rust/blob/master/CONTRIBUTING.md).

*This Week in Rust* is openly developed [on GitHub](https://github.com/rust-lang/this-week-in-rust).
If you find any errors in this week's issue, [please submit a PR](https://github.com/rust-lang/this-week-in-rust/pulls).

## Updates from Rust Community

### Official

### Project/Tooling Updates

* [CGlue Today And The Road Ahead](https://blaz.is/blog/post/cglue-012-and-the-road-ahead/)
* [Black Hat Rust: July Update](https://kerkour.com/blog/black-hat-rust-july-update/)
* [Updates from the Tinyverse - July 2021](https://tinyverse.substack.com/p/updates-from-the-tinyverse-july-2021)

### Observations/Thoughts

* [Towards Inserting One Billion Rows in SQLite Under A Minute](https://avi.im/blag/2021/fast-sqlite-inserts/)
* [Async and asleep: designing our future embedded applications](https://tweedegolf.nl/blog/58/async-and-asleep-designing-our-future-embedded-applications)
* [My Rust development workflow (after 2+ years full-time)](https://kerkour.com/blog/rust-development-workflow/)

### Rust Walkthroughs

* [Awesome Unstable Rust Features](https://lazy.codes/posts/awesome-unstable-rust-features/)
* [video] [How to create an AWS Lambda in rust](https://www.youtube.com/watch?v=PmtwtK6jyLc)

### Miscellaneous

## Crate of the Week

This week's crate is [dylint](https://github.com/trailofbits/dylint), a tool for running Rust lints from dynamic libraries.

Thanks to [George Hahn](https://users.rust-lang.org/t/crate-of-the-week/2704/938) for the suggestion.

[Submit your suggestions and votes for next week][submit_crate]!

[submit_crate]: https://users.rust-lang.org/t/crate-of-the-week/2704

## Call for Participation

Always wanted to contribute to open-source projects but didn't know where to start?
Every week we highlight some tasks from the Rust community for you to pick and get started!

Some of these tasks may also have mentors available, visit the task page for more information.

* [rust-embedded/cross - Call for help: more maintainers wanted](https://github.com/rust-embedded/cross/issues/574)

If you are a Rust project owner and are looking for contributors, please submit tasks [here][guidelines].

[guidelines]: https://users.rust-lang.org/t/twir-call-for-participation/4821

## Updates from Rust Core

280 pull requests were [merged in the last week][merged]

[merged]: https://github.com/search?q=is%3Apr+org%3Arust-lang+is%3Amerged+merged%3A2021-07-12..2021-07-19

* [handle non-integer const generic parameters in debuginfo type names](https://github.com/rust-lang/rust/pull/87082)
* [warn about useless assignments of variables/fields to themselves](https://github.com/rust-lang/rust/pull/87129)
* [suggest a path separator if a stray colon is found in a match arm](https://github.com/rust-lang/rust/pull/87101)
* [add diagnostics for mistyped inclusive range](https://github.com/rust-lang/rust/pull/87071)
* [various diagnostics clean ups/tweaks](https://github.com/rust-lang/rust/pull/87225)
* [compute a better `lint_node_id` during expansion](https://github.com/rust-lang/rust/pull/87146)
* [TAIT: infer all inference variables in opaque type substitutions via `InferCx`](https://github.com/rust-lang/rust/pull/87200)
* [remove refs from `Pat` slices](https://github.com/rust-lang/rust/pull/87140)
* [shrink the `CrateStore` dynamic interface](https://github.com/rust-lang/rust/pull/87117)
* [loop over all opaque types instead of looking at just the first one with the same DefId](https://github.com/rust-lang/rust/pull/87107)
* [cache expansion hash globally](https://github.com/rust-lang/rust/pull/87044)
* [perf: noise and variance](https://github.com/rust-lang/rustc-perf/pull/902)
* [some perf optimizations and logging](https://github.com/rust-lang/rust/pull/87203)
* [update Rust Float-Parsing to use the Eisel-Lemire algorithm](https://github.com/rust-lang/rust/pull/86761)
* [stabilize `[T; N]::map(_)`](https://github.com/rust-lang/rust/pull/87174)
* [split `MaybeUninit::write' into new feature gate and stabilize it](https://github.com/rust-lang/rust/pull/86344)
* [mark Option::insert as `must_use`](https://github.com/rust-lang/rust/pull/87196)
* [added `Arc::try_pin`](https://github.com/rust-lang/rust/pull/85579)
* [hashbrown: replace some custom unsafe code with `array::map`](https://github.com/rust-lang/hashbrown/pull/281)
* [hashbrown: optimize `find`](https://github.com/rust-lang/hashbrown/pull/279)
* [cargo: deduplicate compiler diagnostics](https://github.com/rust-lang/cargo/pull/9675)
* [cargo: add `d` as an alias for doc](https://github.com/rust-lang/cargo/pull/9680)
* [clippy: fix false positives and document `branches_sharing_code` lint](https://github.com/rust-lang/rust-clippy/pull/7462)
* [clippy: new lint: `self_named_constructor`](https://github.com/rust-lang/rust-clippy/pull/7403)
* [clippy: add `Arc` to `redundant_allocation`](https://github.com/rust-lang/rust-clippy/pull/7308)
* [clippy: fix ICE in `is_integer_const`](https://github.com/rust-lang/rust-clippy/pull/7473)

### Rust Compiler Performance Triage

A very quiet week with only improvements. There was one possible regression, but it was removed from consideration due to only barely impacting a somewhat noisy stress-test benchmark. Untriaged pull requests continue to pile up, but there is still not a good process for dealing with them. 

Triage done by **@rylev**.
Revision range: [5c0ca08..998cfe5](https://perf.rust-lang.org/?start=5c0ca08c662399c1c864310d1a20867d3ab68027&end=998cfe5aad7c21eb19a4bca50f05a13354706970&absolute=false&stat=instructions%3Au)

0 Regressions, 3 Improvements, 0 Mixed; 0 of them in rollups

[Full report here](https://github.com/rust-lang/rustc-perf/blob/master/triage/2021-07-27.md).

### Approved RFCs

Changes to Rust follow the Rust [RFC (request for comments) process](https://github.com/rust-lang/rfcs#rust-rfcs). These
are the RFCs that were approved for implementation this week:

* [#[derive(Default)] on enums with a #[default] attribute](https://github.com/rust-lang/rfcs/pull/3107)

### Final Comment Period

Every week [the team](https://www.rust-lang.org/team.html) announces the
'final comment period' for RFCs and key PRs which are reaching a
decision. Express your opinions now.

### [RFCs](https://github.com/rust-lang/rfcs/labels/final-comment-period)

* [Stabilize Cargo's weak-dep-features and namespaced-features.](https://github.com/rust-lang/rfcs/pull/3143)

### [Tracking Issues & PRs](https://github.com/rust-lang/rust/labels/final-comment-period)

* [disposition: merge] [Allow reifying intrinsics to fn pointers.](https://github.com/rust-lang/rust/pull/86699)
* [disposition: merge] [Associated functions that contain extern indicator or have #[rustc_std_internal_symbol] are reachable](https://github.com/rust-lang/rust/pull/86492)
* [disposition: merge] [Commit to not supporting IPv4-in-IPv6 addresses](https://github.com/rust-lang/rust/pull/86335)
* [disposition: merge] [Implement Extend<(A, B)> for (Extend<A>, Extend<B>)](https://github.com/rust-lang/rust/pull/85835)

### New RFCs

*No new RFCs were proposed this week.*

## Upcoming Events

### Online

* [July 27, 2021, Dallas, TX, US - Last Tuesday - Dallas Rust](https://www.meetup.com/Dallas-Rust/events/jqxqwrycckbkc/)
* [August 3, 2021, Buffalo, NY, US - Buffalo Rust User Group, First Tuesdays - Buffalo Rust Meetup](https://www.meetup.com/Buffalo-Rust-Meetup/events/jxfdjsycclbfb/)
* [August 10, 2021, Seattle, WA, US - Monthly meetup - Seattle Rust Meetup](https://www.meetup.com/Seattle-Rust-Meetup/events/gskksrycclbnb/)

### North America

* [July 27, 2021, Chicago, IL, US - Rust in production at Tempus - Chicago Rust Meetup](https://www.meetup.com/Chicago-Rust-Meetup/events/279131036)
* [August 11, 2021, Atlanta, GA, US - Grab a beer with fellow Rustaceans - Rust Atlanta](https://www.meetup.com/Rust-ATL/events/lhpkmsycclbpb/)

If you are running a Rust event please add it to the [calendar] to get
it mentioned here. Please remember to add a link to the event too.
Email the [Rust Community Team][community] for access.

[calendar]: https://www.google.com/calendar/embed?src=apd9vmbc22egenmtu5l6c5jbfc%40group.calendar.google.com
[community]: mailto:community-team@rust-lang.org

# Rust Jobs

**The Tor Project**

* [Software Developer, Rust (Remote)](https://www.torproject.org/about/jobs/rust-dev/)

**Stockly**

* [Back-end developer - TechOps team (Rust, GRPC, PostgreSQL) (Paris, FR)](https://www.welcometothejungle.com/fr/companies/stockly-1/jobs/back-end-developer-rust-grpc-postgresql_paris)

**Rhebo GmbH**

* [Rust Software Engineer - Focus Networks (DE)](https://germantechjobs.de/en/jobs/Rhebo-GmbH-Softwareentwickler-Rust---Schwerpunkt-Netzwerk-wmd)

**Kraken**

* [Senior Banking Engineer - Rust (Remote)](https://jobs.lever.co/kraken/2863623f-13c9-4f50-992d-7c25736a60f9)
* [Senior Backend Engineer - Rust - Core Backend (Remote)](https://jobs.lever.co/kraken/4c864c8f-bde6-443d-b521-dd90df0e9105)

**Lumeo**

* [Senior Backend Engineer (Rust) (Remote EU)](https://www.lumeo.com/careers/senior-backend-engineer-rust)
* [Senior Systems Engineer (Rust) (Remote EU)](https://www.lumeo.com/careers/senior-systems-engineer-rust)

**Tweede golf**

* [Lead Developer Embedded Rust (Nijmegen, NL)](https://tweedegolf.nl/vacatures/2/lead-developer-embedded-rust)
* [Embedded software engineer (Nijmegen, NL)](https://tweedegolf.nl/vacatures/11/medior-embedded-engineer)

**Kollider**

* [Junior Backend Engineer (Remote)](https://kollider.homerun.co/junior-backend-engineer/en)
* [Senior Backend Engineer (Remote)](https://kollider.homerun.co/senior-backend-engineer/en)
* [DevOps Engineer (Remote)](https://kollider.homerun.co/devops-engineer/en)


*Tweet us at [@ThisWeekInRust](https://twitter.com/ThisWeekInRust) to get your job offers listed here!*

# Quote of the Week

> Tip: whenever you wonder if Pin could be the solution, it isn't

– [@SkiFire13 on the official Rust Discord](https://discord.com/channels/442252698964721669/448238009733742612/866312170890330122)

Thanks to [Kestrer](https://users.rust-lang.org/t/twir-quote-of-the-week/328/1071) for the self-suggestion!

[Please submit quotes and vote for next week!](https://users.rust-lang.org/t/twir-quote-of-the-week/328)

*This Week in Rust is edited by: [nellshamrell](https://github.com/nellshamrell), [llogiq](https://github.com/llogiq), and [cdmistman](https://github.com/cdmistman).*

<small>[Discuss on r/rust](https://www.reddit.com/r/rust/comments/k5nsab/this_week_in_rust_367/)</small>
