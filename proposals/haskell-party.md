# Haskell Party Community Maintenance


## Pre-ramble

This is partially a WIP proposal for an initiative I would like to work
on, and partially something I already started working on. It does
not require any external resources and I could just get on with
it, but I would like to solicit some feedback on the direction. Do you
think this is a good idea? Are there alternatives you would prefer?
Feel like nit-picking? Can this get a stamp of approval from the HF
stability WG?

## Preamble

Haskell tooling is in large part built and maintained by
volunteers. This puts the ecosystem at risk as individuals may leave,
in turn leaving their tools unmaintained.

If a package is unmaintained, or not getting enough attention, it may
hold back parts of the ecosystem from updating to new releases of GHC
or other packages.

I suspect that a common cause for packages becoming unmaintained is
the churn needed to keep up with the ecosystem. Breaking changes occur
often compared to a lot of other languages, and when following the PVP
you often need to update your package to say that you have verified
that it still works.

We have a few ways to combat the risk of inactive maintainers:

* Encourage maintainers to find additional maintainers
* Hackage revisions and Non-Maintainer Uploads done by Hackage Trustees
* The Hackage Package Takeover procedure
* Forking

I think that the best solution is for every package has multiple
active maintainers that can chip in when necessary. This might be the
hardest thing to do as the community often only realizes that the need
exists when maintainers have left.

The goal of this proposal is to help with packages that struggle with
active maintanence by offloading the original maintainer and letting
the community benefit from more actively maintained packages.

## Haskell Party (working title)

I created the [haskell-party GitHub
organization](https://github.com/haskell-party) where I currently host
packages that I do not actively develop but would like to see kept up
to date for the community's sake. I want to add more packages, but I
would not have the time to maintain all of them by myself.

## Terminology

I struggled a bit with naming the roles as the terms "admin" and
"maintainer" conflicts with GitHub and Hackage. This might not make
sense until you have read the rest, but here's what I ended up with:

* Haskell Party Board (member): Decision making body for the whole project.
* Haskell Party Steward: Doing the administrative work for the whole
  project. Akin to Hackage Trustees and Stackage Curators.
* Project Maintainer: Manages an individual Haskell project/package.

### Haskell Party Projects

A Haskell Party Project is a Haskell library or application: a git
repository with a Cabal file, essentially.

### Project maintenance

Haskell Party Projects need to have at least two Project Maintainers
that are GitHub project admins (meaning they can add new admins, and
do everything else) and Hackage maintainers (meaning they can perform
uploads and appoint new Hackage maintainers).

### Who would benefit from joining?

Joining Haskell Party is voluntary. It is not a goal to try to get
every maintainer and package to join. Rather, I hope that people that
feel that the maintenance burden is too high will want to join to get
assistance.

* Package authors that do not have time to keep their projects up to date.

* Library users who have had to go through the package takeover or NMU
  processes to patch a library that they use, but do not intend to
  maintain.

* Maintainers who would like help with finding backup maintainers.

We will of course want more maintainers to join and bring their
packages, but we must not be pushy. Simply asking "Would you like
help with maintenance this package?" might be enough. I see no reason to
reach for packages that already seem well-maintained.

### Requirements for joining

The requirements for getting a project into the Haskell Party should
be fairly lax. Since people may not have a lot of time, asking them to
jump through hoops seems counter-productive. But there are a few
important points.

A project must:

* be intended for usage by others in the community
* have been uploaded to Hackage - This goes hand-in hand with the
  above.
* be transferred to the Haskell Party organization - GitHub does not
  allow multiple project admins when a project resides under a
  user's namespace
* Add the `HaskellParty` user as a maintainer on Hackage
* (for projects residing in another organization) add at least one Haskell
  Party Steward as an admin in its github organization - otherwise we cannot appoint
  new maintainers if the need arises.

The original maintainer must:

* Allow other maintainers to at least keep the package up to date by
  making patch releases or revisions. This will be a gentleman's
  agreement due to technical access control.


### Haskell Party Stewards

Stewards will do the meta work needed to maintain the organization.

They are admins of the GitHub Organization, meaning they can
administer access to all projects within it.

Even though Stewards have all the required permissions, they are not
considered maintainers of the projects. They should leave any work on
the projects to the actual maintainers. Stewards are free to volunteer
to be maintainers for individual projects.

The main tasks for the Stewards is to handle the transfer
of projects to the organization, and to find new maintainers any
projects that need them.

Stewards are free to organize their work as they see fit. Be it a weekly
rotation or responsibility for certain areas.

The number of Stewards will depends on how popular Haskell Party
becomes, more can be added as needed.

Stewards can stay on for as long as they like. There will be the
occasional check-in to see if Stewards want to remain as such.


### Haskell Party Board

The Haskell Foundation recommends setting up a turnover for any
decision making bodies, see [What does affiliation
entail?](https://haskell.foundation/affiliates/about/). The Haskell
Party Board would be the decision makers and initially comprise of the
Haskell Party Stewards.

There will always be at least two Stewards on the board as decisions may
impact their workload, or how they work.

The board will make decisions regarding Stewards and handle the
evolution of policies related to Haskell Party Projects.

Since being a Steward includes wide permissions to the projects in the
organization, there could arise a need for the board to intervene.

Turnover timing and mechanisms are TBD.

## Onboarding a project

1. Haskell Party Stewards will initiate a transfer of the repository.
2. Haskell Party Stewards or the original maintainer will look for
   additional maintainers.
3. The new maintainers will make sure that the "Requirements on
   maintenance" (see below) are met.

## Requirements on maintenance

The only thing I think we really need is:

* Working CI. This is easy to set up using
  [haskell-ci](https://github.com/haskell-CI/haskell-ci)
* An up to date list of at least three maintainers (The Stewards can
  help with finding maintainers)
* A willingness to keep packages up to date. This may be done by
  joining [Stackage](https://www.stackage.org/), by maintainers
  subscribing to [packdeps](https://packdeps.haskellers.com/), or by
  being active in merging pull requests.

Future requirements could touch on a lot of the same points that were
suggested in [Maintainership
standards](https://github.com/haskellfoundation/stability/issues/7) by
@goldfirere. But I think we should start small here and see how it
goes. If we decide to add additional requirements we should expect to
source the work needed for existing projects from the community,
rather than requiring it from existing maintainers.

## Leaving Haskell Party

Maintainers are free to move their package out of the
organization. The original maintainers will be project admins on
Github so they are free to transfer it out. Otherwise, if a majority
of maintainers would like to transfer then they would need to request
this from the Haskell Party Stewards. Hackage does not have categories
of maintainer permissions, so any Hackage maintainer can remove other
maintainers.


## Workflows

I imagine a GitHub driven workflow for most things.

Haskell Party will contain a meta-repository where everything related
to the project can be discussed.

The issue tracker can be used for questions about the status of
packages, or suggestions for how we should operate.

Pull requests can be used to initiate adding new packages to the
organization, with templated checklists for what needs to be done.

The repository will also contain templates to post in other
venues. Such as calls for maintainers, a short "Would you like to
join? Here is what we do: ..."


## Access Control

### Github
* Stewards & the board will be organization owners, giving them
  access to everything on GitHub.
* The initial Project Maintainer will be a GitHub repository admin of
  their repository, they are then free to manage permissions as they
  please. They need to appoint at least one more repository admin.

### Hackage
* Stewards will have access to a `HaskellParty` account that is added as a
  maintainer of every haskell-party project as part of
  onboarding. This user will not be in the uploader group, meaning it
  can not upload new releases. The password will be known by all
  Stewards, and will be rotated every time a Steward steps down.
* Maintainers will be Hackage maintainers so that they can perform uploads.

## But who will do the work?

Ideas are great and all, but getting this up and running requires some
work. Initiatives based on voluntary effort often fail even if the
workload is small.

I (@bergmark) would like this to happen, and I'm willing to invest the
time to get it rolling and I can join as a Board member and Steward.

I would initially reach out to some members of the community that I
trust, to see if they would like to help out as board members and/or
stewards.

I think I could manage the initial workload on my own, but going
forward it would defeat the point if I was a single point of failure!

## Risks

Perhaps no one wants to join. Perhaps there will be intiial interest
in the project that wanes. I'd be a little sad, but then I would be
free to do something else. Since no project is locked in the
organization, they could be transferred if the need arises.

Maintainers may feel pressured to join, or they may have joined but
are dissatisfied with the organization. We need to do our best to
emphasize that it is voluntary, and that they are always free to
leave. If they don't see the benefit, then they should not join! We
also need to make sure that any decisions we make regarding
maintenance requirements do not cause undue work.

Stewards and the Board will have wide access to the projects in the
organization. We may want to enforce some security measures such as
2FA to mitigate the risks of a hostile takeover.

## What's next?

Firstly I would like to gather some feedback on the idea as a
whole. Is this something you think we should move forward with? This
will be posted as a Stability WG proposal, and posted to Discourse.

If that goes well, I will send out a call for the initial set of Board
Members and Stewards to get everything rolling.

We will need to draft an "open for business" post that summarizes this
proposal to let people know that they can join along with their
projects.

We should also draft some form of checklist for what Stewards need to
do when onboarding projects and for the periodic tasks that should be
performed (e.g. should there be a check for active maintenance every
now and then, or should we look for inactivity in other ways?).

If anyone has a package they would like to transfer over before
everything is settled, let me know!
