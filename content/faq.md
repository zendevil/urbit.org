+++
title = "FAQ"
template = "page_indiced.html"
[extra]
hidetitle = "true"
index = "true"
+++

### What is Urbit? {% #what-is-urbit %}

Urbit reimagines the internet as a peer-to-peer network designed to stay that way. Previous attempts to "decentralize" the internet have only attempted to solve certain corners of the problem. Urbit proposes that only a new stack, built from the ground up as a tightly integrated system, can realize a great user experience for people using a peer-to-peer web.

Combining a deterministic operating system ([Urbit OS](#what-is-arvo) / Arvo) and a secure, global identity layer ([Urbit ID](#what-is-urbit-id) / [Azimuth](#what-is-azimuth)), the Urbit project has created something that’s never existed before: an encrypted [Sybil resistant](https://en.wikipedia.org/wiki/Sybil_attack) peer-to-peer network where you can be sure that messages are never tampered with or surveilled.

The connected world anticipated by Urbit is a much friendlier one, much like the early Internet, where collegial discussion and collaboration was the norm. Problems that are unsolvable without large-scale political centralization in our current internet – data breaches, spam, fake reviews, malware-spreading, harassment – become tractable when individuals control their computing again. You have one login for everything. You own and control all of your software and all of your data by default. Software is designed around the friendships, families, communities, and organizations you're already a part of – not the other way around.

### How can I contribute to Urbit? {% #contribute %}

We encourage outside contributors to become a part of the project. The best way to do this is to check out [Urbit](https://github.com/urbit) on GitHub, look at the pinned repositories, and check out our [Contributing](/docs/development/develop) guide. After you've gotten familiar with the system, feel free to open issues and make pull requests.

### Who is building Urbit? {% #who-builds-urbit %}

[Tlon](https://tlon.io), a San Francisco-based company, is the primary developer of Urbit, along with [various independent developers](https://github.com/urbit/urbit/graphs/contributors) and [urbit.live](https://urbit.live).

## Urbit ID

### What is Urbit ID? {% #what-is-urbit-id %}

Urbit ID is the identity system utilized by Urbit, which associates to each [ship](/docs/glossary/ship) a public and private key used to establish encrypted connections between one another and to guard private data. For [planets](/docs/glossary/planet), [stars](/docs/glossary/star), and [galaxies](/docs/glossary/galaxy), this is achieved with a set of Ethereum smart contracts called [Azimuth](#what-is-azimuth). Keys for [moons](/docs/glossary/moon) and [comets](/docs/glossary/comet) are handled within Urbit.

### What are stars, galaxies, and planets? {% #stars-galaxies-planets %}

Urbit IDs come in three classes: galaxies, stars, and planets. The length of an identity’s name will tell you its class. Galaxies are 8-bit and have names like `~mul`. Galaxies issue 16-bit stars (`~dacmul`), which can themselves issue 32-bit planets (`~laptel-holfur`).

Planets are intended for everyday use by individuals, and there are 4.3 billion of them (two to the 32nd power). Stars and galaxies, on the other hand, are meant to act as network infrastructure: on the [Urbit OS](#what-is-arvo) network they provide routing and are responsible for distributing software updates.

### How can I spend less to get a planet? {% #gas-prices %}

Using Ethereum has become much more expensive since Urbit ID first launched. To rectify this, Tlon has created a system referred to as [naive rollups](/docs/glossary/rollups), or "layer 2". By reducing the size of transactions, batching them together, and moving computation off-chain to your urbit, it is now possible to perform Urbit ID transactions free of charge and without any prior knowledge of blockchains, cryptocurrency, or Ethereum. This is easily done using [Bridge](/docs/glossary/bridge), our web interface for managing your Urbit ID.

### What is Azimuth? {% #what-is-azimuth %}

[Azimuth](/docs/glossary/azimuth) is what we call the set of Ethereum contracts that make up a general-purpose decentralized PKI ("public key infrastructure") utilized by Urbit ID. It keeps a record of which Ethereum addresses own which Urbit planets, stars, and galaxies, as well as the public keys associated with those ships.

It's also kind of a [cool astronomical concept](https://en.wikipedia.org/wiki/Azimuth).

### How many planets, stars, and galaxies are active? {% #how-many-planets-stars-galaxies %}

The raw data on most Urbit ID / Azimuth events that have occurred can be found [on the Azimuth website](https://azimuth.network/stats/events.txt). We’re currently working on generalized tooling for viewing these events.

You can also inspect and execute functions in the [azimuth.eth](https://etherscan.io/address/azimuth.eth#code) contract on Etherscan.

### What are comets and moons? {% #comets-moons %}

In addition to the three classes of identities mentioned above, there are two other kinds of Urbit [ship](/docs/glossary/ship)s that are _not_ registered in the Urbit ID / Azimuth contracts.

[Moons](/docs/glossary/moon) are 64 bits, issued by [planets](/docs/glossary/planet), and have names like `~doznec-salfun-naptul-habrys`. Moons are meant for connected devices: phones, desktops, smart TVs, digital thermostats, and other IoT devices. Moons are subordinate to their parent planet. A strong analogy here is that ordinary social media sites are somewhat like planets, and your account on them is a moon. Urbit elevates everybody to the level of planet.

[Comets](/docs/glossary/comet) are 128 bits and have no parents. They can be launched by anyone for free. Since their identity is not maintained on the blockchain, they will likely not be trusted by default by others on the [Urbit OS](#what-is-arvo) network, though you shouldn't have any problem until the network grows much larger. They have long, hard-to-memorize names, like `~racmus-mollen-fallyt-linpex-watres-sibbur-modlux-rinmex`.

### What is a `@p`? Why is my username generated for me? {% #what-is-patp %}

A `@p` ([pronounced](/docs/hoon/hoon-school/hoon-syntax#reading-hoon-aloud) _pat-pee_) is a name like `~zod` or `~lodleb-ritrul` composed of pronounceable, three-letter phonemic elements like `zod`, `lod`, `leb`, `rit` and `rul`. Shorter names, such as `~zod` and `~marzod`, are assigned to [ship](/docs/glossary/ship)s with special duties on the [Arvo](#what-is-arvo) network galaxies and stars, respectively. Longer names like `~palfun-foslup` are identities for typical users.

These names map directly to a corresponding number in the Urbit ID address space. Galaxies occupy the 8-bit address space, so any galaxy is actually a number between zero and 255. Stars occupy the 16-bit address space, and planets occupy the 32-bit address space.

Your name is generated for you as a solution to [Zooko's triangle](https://en.wikipedia.org/wiki/Zooko%27s_triangle), which roughly states that names on a network protocol can only be two of (i) human-meaningful, (ii) secure, and (iii) decentralized. Urbit chooses (ii) and (iii), while something like DNS chooses (i) and (ii).

Regardless, you can always choose to set your nickname in [Landscape](#what-is-landscape), so if you wish for a different name to be displayed then you have the freedom to do so.

### Can I change my `@p`? {% #change-my-patp %}

Nope. There is a 1:1 mapping between name and identity. Think of your `@p` sort of like a phone number. It's just a random synthetic name that doesn't leak any personal information about you.

### How do I get an identity? {% #get-an-identity %}

The easiest way is to find a friend who can give you one. They're out there — just ask around. You'll have a good chance of meeting one if you join Urbit Community, the default group for new [ship](/docs/glossary/ship)s at `~bitbet-bolbel/urbit-community`, as a [comet](/docs/glossary/comet) and contribute pleasantly to the conversation.

Or, if you must, try an ERC-721 (NFT) exchange (Google or Twitter should help you with this). This will probably involve a purchase and a transfer to an Ethereum address that you own. We recommend using [Bridge](/docs/glossary/bridge), available at [https://bridge.urbit.org](https://bridge.urbit.org), to access the address that the identity is transferred to.

### How do I transfer an identity to someone else? {% #transfer-identity %}

Access the Ethereum address that holds the identity you wish to transfer via [Bridge](https://bridge.urbit.org).

### What is the best way to access my Urbit ID? {% #access-azimuth %}

We recommended using [Bridge](https://bridge.urbit.org) for all Urbit ID-related operations. It’s great for managing your identities, as well as for viewing information about identities you don’t own.

Be careful about using online versions of Bridge not hosted on urbit.org. Since Bridge touches your private keys, it can also steal them.

### Why aren't there more planets? {% #more-planets %}

Urbit is designed to be as simple as possible. The sponsorship tree for Urbit ID simply expands by squaring the size of the last tier. That is, there are <span class="mono">2^8^ (256)</span> [galaxies](/docs/glossary/galaxy), <span class="mono">(2^8^)^2^ = 2^16^ (~65K)</span> [stars](/docs/glossary/star), <span class="mono">(2^16^)^2^ = 2^32^ (~4B)</span> [planets](/docs/glossary/planet). There are <span class="mono">2^64^</span> [moons](/docs/glossary/moon) — but moons are tethered to their planet, unlike stars and planets.

This pattern exists because it’s a simple way to enforce the scarcity of addresses and build a friendly network. When a tier of the address space begins to be populated, we start populating the next tier down. When Urbit nears the limit of <span class="mono">2^32^ (4B)</span> planets, we’ll figure out a way to populate the <span class="mono">2^64^</span> moons. The galaxies that govern the Urbit ID contracts can always vote to upgrade them — and we expect that they will.

The problem with populating the moons now is that <span class="mono">2^64^</span> is a _really, really big_ number. We’ll need some way of differentiating between humans and their devices (to prevent devices turning into rogue botnets). But that’s a hard problem, and we prefer to start with the simplest possible solution before solving hard problems. The current scheme works. Once we need to update it, we’ll figure it out.

The number of addresses is in a sort of 'Goldilocks zone' for preventing spam. Too many addresses will result in them being very cheap and thus spammers can just acquire more once they get blocked. Too few addresses and they end up too expensive for the average user. The technical term for what the finite address space bestows upon the network is [Sybil resistance](https://en.wikipedia.org/wiki/Sybil_attack), a very important property for any decentralized network.

It’s also worth noting that, while there are almost 8B people on Earth, there are almost certainly not 8B internet users. Facebook has about 2.5B users, Apple has about 1B. Urbit has a long way to go before we get close to <span class="mono">2^32^</span>.

(For more background on why Urbit ID is the way it is, read [this](/understanding-urbit/urbit-id/).)

### I have a galaxy or star with lockup conditions. How does this work? {% #lockup-conditions %}

There are two kinds of release schemes for locked up assets: linear and conditional.

In either scheme, you start out being able to take one star out of lockup, regardless of the terms set around the lockup as a whole. This way, you get to participate with a star right away. Go do something cool!

If your lockup involved a [galaxy](/docs/glossary/galaxy), all of its [stars](/docs/glossary/star) will be locked up, but you will have immediate, lock-free control of the galaxy. You will likely need it to use that star.

Note that the "releasing" of stars just means that they become available for you to claim. They don't automatically get transferred to you; you have to withdraw them from the appropriate lockup contract.

Linear release is the simplest: your stars will be released linearly over a period of time. Most often this is a period of four years. If you have four stars in lockup, that means you will be able to withdraw one star per year. In many cases, there is also an initial windup period which has to pass before linear releasing begins, typically one year. Since Azimuth launched in January 2019, the linear release will begin in January 2020.

Conditional release is a bit more complicated. If your stars are in conditional lockup, they're likely divided over three so-called tranches. Each of these unlocks only after a unique condition is met. Since it's difficult to verify things about the real world using smart contracts, the [Galactic Senate](/docs/glossary/senate) verifies that they've been met. Once the Senate marks a condition for a tranche as cleared, it starts releasing linearly over the period of a year.

### How secure is Urbit right now? {% #how-secure-is-urbit %}

We consider some parts of Urbit to be secure, while other parts still need some work and external auditing. For technical details on Urbit's cryptosystems, see the [documentation](/docs/system-overview/cryptography).

[Urbit ID](#what-is-urbit-id) / [Azimuth](#what-is-azimuth), Urbit's identity layer, is live on the Ethereum blockchain and has been audited by Open Zeppelin, Blockchain at Berkeley, and Bloctrax.

In late 2020, Urbit's [Ames](/docs/glossary/ames) networking protocol was audited by [Leviathan Security](https://www.leviathansecurity.com/). You can read about this milestone [here](/blog/security-and-continuity).

The security of the runtime, [Vere](/docs/vere/), has not yet been adequately assessed or systematically hardened.

All communication on Urbit is end-to-end encrypted. However, the [event log](/docs/glossary/eventlog) is not encrypted at rest but we plan to give users that option in the future.

Tlon keeps a quantum computing expert on staff and understands that post-quantum cryptographic methods must be implemented sooner than later, since any data not already encrypted using these methods is at risk of being collected and decrypted once sufficiently powerful quantum computers exist. [NIST](https://www.nist.gov/) anticipates the release of their preliminary findings on [post-quantum cryptography standards](https://csrc.nist.gov/projects/post-quantum-cryptography) around the end of 2021, with full guidelines following in 2024. Tlon will develop a strategy for post-quantum encryption for Urbit following their recommendations.

Thus, while Urbit is probably more secure and private than most digital communication channels, we cannot yet consider it impervious to a dedicated attacker. If you are a cybersecurity expert looking for work, please drop us a line at `apply@tlon.io`.

## Urbit Grants

### What are the different types of grants? {% #grants-1 %}

There are three ways to receive a [grant of stars](https://grants.urbit.org/) for your contribution to the Urbit ecosystem.

- You can submit a **Proposal** if you’re interested in working on a project of your own creation for a number of stars that you pitch.
- You can apply to claim a **Bounty.** Bounties are requests for work created by Tlon that are claimable by the public, with a predetermined number of stars as the reward.
- The **Gifts** program, which is Tlon’s informal way of rewarding contributions that don’t fall into the above categories. There is no way to apply for a gift.

### How do I get a gift? {% #grants-2 %}

Make useful and substantial contributions to Urbit. These can be contributions to the project itself, or they can be outside tools that aren’t part of the Urbit codebase. There’s no formal system for determining who gets a gift; it’s at the discretion of employees at Tlon. Nothing is guaranteed, but you can get an idea for what kinds of contributions results in gifts by looking at the [gifts history](https://grants.urbit.org/history).

### How often are gifts awarded? {% #grants-3 %}

Gifts are awarded semiannually.

### Do gifts follow a set size? {% #grants-31 %}

Gifts do follow a structure. A gift can be in one of three categories of sizes: Gold, Silver, or Bronze. Gold gifts award the most stars, Bronze gifts award the least. These categories don't correspond to a set number of stars being awarded. That number will likely change as the project matures and star values increase. That's why you see many more stars being awarded as the earliest gifts in the [history section.](https://grants.urbit.org/history)

### What happens if a user does not complete a proposal but meets some milestones? {% #grants-4 %}

You must complete the proposal to be guaranteed to receive the star grant. Partial star payouts can be negotiated for incomplete work, but such payouts are at the discretion of Tlon.

However, either party may terminate a proposal on seven days’ written notice. In such a scenario, you may be paid pro rata for any portion of the proposal that has been completed.

### Do star rewards from grants have lockup conditions? {% #grant-5 %}

No.

### Do I have to pay taxes on stars? {% #grant-6 %}

Yes. In the United States, stars are considered to be income. If you are American, we need your W-9 before we can pay out your stars. If you’re not an American, you don’t need to get us any forms, but you do need to personally follow the relevant tax laws in your jurisdiction.

### Can I create a bounty? {% #grants-7 %}

No. Bounties are only created by Tlon, but we draw inspiration for bounties from various sources, including the community. If you want to pitch a project, use the Proposals system.

### How are proposals approved? {% #grants-8 %}

The manager of the Grants program approves them after consulting with the relevant members of the engineering team. This proposal can be accepted, rejected, or accepted with changes by Tlon. The proposal’s star payout can also be adjusted.

### If I win a proposal, do I have an exclusive claim on the project? {% #grants-9 %}

You have a claim to the reward of the project as long as milestones are met to the satisfaction of Tlon. However, Tlon may allow another developer to work on the same project in parallel, for a separate reward.

### Will milestones be embedded in a smart contract? {% #grants-10 %}

No.

### Does reputation play a role in the assessment of grants? {% #grants-11 %}

Yes. We consider this to be a feature.

### I completed a proposal. When will I receive payment? {% #grants-12 %}

We will pay you within a 30-day window.

### Can I see the proposals of others that have been accepted? {% #grants-13 %}

Yes. Check out our [proposals page.](https://grants.urbit.org/proposals)

### How do I safely store my stars? {% #grants-14 %}

We recommend storing each star in its own Ethereum wallet. The private keys to these wallets should be stored on physical media that is not connected to a networked computer. Redundancies don’t hurt!

### Can I delegate a bounty or proposal to someone else? {% #grants-15 %}

No, not unless explicitly authorized by Tlon.

### Do I need to sign a contract? {% #grants-16 %}

After you are approved to work on a bounty or a proposal, you will be sent a contract that you'll need to sign. You don't need to sign a contract to receive a gift, though.

Here are a few important points from the bounty and proposal contracts:

- **Intellectual property:** You agree to commit all intellectual property you create in connection with the relevant bounty or proposal. You agree that you won’t incorporate any IP that is licensed in a conflicting way.

- **No conflicts:** You agree that you are not subject to any restrictions that would interfere with your ability to complete the bounty or proposal.

- **No employment relationship:** You agree that being approved for the grant or bounty does not imply any employment relationship with Tlon.

- **Termination:** Either party (you or Tlon) can terminate the agreement on seven days' written notice. If that happens, you may be compensated _pro rata_ for the amount of work you've completed, but this compensation is at the sole discretion of Tlon.

- **Governing law:** The agreement is governed by the laws of the State of California.

Note that these paraphrased points are just for summarization purposes. The language in contract that you receive and sign is the only source of authority for the grant agreement.

## Miscellaneous

### Who is Curtis? {% #who-is-curtis %}

Urbit started back in 2002 as Curtis Yarvin’s personal project. Curtis developed the original prototype for Urbit and, separately, wrote a blog on history and politics under the pen name ‘Mencius Moldbug’.

In early 2019, Curtis left Tlon and the Urbit project. He gave Tlon all of his
voting interest in the network (his galaxies), and he no longer owns any Tlon
stock. He retains a non-voting, minority interest in the address space — but is not involved in the day-to-day development or operations.

Curtis laid the foundation for Urbit by delivering its first prototype but, since 2013, it has been refined and almost entirely rewritten by a community of developers. No one working on Urbit today had anything to do with Curtis’s writing. For the most part, we couldn’t be less interested in it.

The community of people who build Urbit have widely varied ways of thinking and looking at the world, but they all share two things: the desire to build neutral infrastructure for all people and to think from first principles about hard problems. We welcome spirited debate and disagreement as a primary tool for refining our work. Successful infrastructure, we think, serves all people — no matter their background, culture, or worldview.

### Why do you use Ethereum? {% #why-eth %}

In 2019 (when [Azimuth](#what-is-azimuth) was launched), Ethereum was the most widely deployed, most secure, and best documented general purpose blockchain, and it remains so today. Using Ethereum is a practical engineering choice. It’s the best way to bootstrap real cryptographic ownership. We’re not specifically interested in Ethereum one way or the other.

One day we’d really like the Urbit ID registry to be hosted on [Urbit OS](#what-is-arvo) itself. But the first challenge is getting Urbit OS to be completely secure.

### Why is Hoon so weird? {% #why-hoon %}

There are things about Urbit that are weird by design, and some that are weird because we haven’t gotten around to cleaning them up. [Hoon](/docs/glossary/hoon), for the most part, is weird by design, but there are a few things about it we’d like to clean up. For a complete description of why we created Hoon, see the [Hoon overview](/docs/hoon/overview).

The runes are, once you get the hang of them, pretty nice. Your mileage may vary, of course, but many talented engineers have spent many, many hours writing Hoon. It’s a simple, practical language. But the learning curve can be a bit high.

The standard library and naming is something we’ve discussed changing, and it could happen. It’s definitely up for debate whether or not the four-letter naming convention works well. The vanes (kernel modules) have largely moved away from this convention.

The right way to think about Hoon is as the ‘C of Urbit’. It’s a bare bones language that gets you pretty close to Nock. Eventually, we’ll probably implement more expressive languages that compile to Urbit. But for now, satisfy your curiosity and [sign up for Hooniversity](https://hooniversity.org/), a community led Hoon educational organization.

Another option is to treat [Urbit as an API](/docs/arvo/eyre/external-api-ref), which allows one to use common languages such as Python and Javascript to build userspace programs. For now this option is not as powerful as Hoon, but there is still a lot that a developer without the time or inclination to learn Hoon can do.

### What is the point of Nock? {% #why-nock %}

The primary technical reason it is difficult for the individual to run a personal server is that modern computing architectures are not deterministic. What solves a problem for one person is not guaranteed to work on another person's computer, even if they are using identical hardware. [Nock](/docs/glossary/nock) solves this problem. It provides a single computing foundation for the whole network, so that difficult issues that arise when running a server need only to be solved once and the solution is guaranteed to work for everyone on the network.

It’s true that Nock, without jets, is slow. With the ability to call out to a native function, it’s not so bad. This is done by our runtime, [Vere](/docs/glossary/vere), a Nock interpreter written in C.

### Can I host my Urbit with someone else? {% #why-hosting %}

Yes, [Tlon](/blog/hosting-the-future) and [a few others](/blog/providers) began [accepting signups](https://tlon.io) to provide hosting service in 2020. Under this arrangement, Tlon does all the work of setting up cloud infrastructure and getting your planet up and running, making getting started with Urbit as simple as signing up for an ordinary online service.

Should you one day wish to run your Urbit yourself, any hosting provider ought to offer you the ability to download your [ship](/docs/glossary/ship)'s [pier](/docs/glossary/pier) to your own device and do so. This is a very low friction process thanks to Urbit's deterministic design.
