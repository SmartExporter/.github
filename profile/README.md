```
JANUARY 2023

The SmartExporter team has hosted code on Azure DevOps for a decade

https://dev.azure.com/tripitaka/

We are moving now that CaseWare acquired our assets. The migration will
happen gradually. The Tripitaka organization has 70+ repositories and
the CaseWare organization has 93 in January 2023. Simply dumping our
repositories into CaseWare is not ideal since we could double the repo
count. Plus we have naming conflicts across projects. This move will
take years to complete.

Step 1
    Clone public repositories in GitHub. Apply security policies.
    Gradually invite members.

Step 2
    Migrate real project. Build on GitHub, publish NuGet packages.
    Test. Verify. Test.

Step 3
    Migrate other projects. GitHub becomes primary Azure Devops
    secondary.

Step 4
    Resolve CaseWare/SmartExporter repository conflicts.

Step 5
    Merge organizations or keep them separate (undecided)


MARCH 2023

SHUTDOWN AZURE DEVOPS
    Turning off the Azure DevOps spigot is easy. We have 73+
    projects. Once a few initial projects are running on GitHub
    it becomes a matter of time per repo. We estimate it takes
    2 man hours to migrate a repo from Azure DevOps to GitHub.
    About 73h * 2h = 146h. Add another 60 hours for figuring out
    how to do stuff. Round it up to about 210 hours.

    Our build process is central to daily activities. We kick off
    hundreds of builds each day. Developers gain little migrating
    to GitHub since our existing systems are a decade old and do
    what they need to. We are reinventing what we already have.

    SmartExporter is an active product with contractual obligations.
    Moving to GitHub will not earn us an additional cent. We cannot
    dedicate all time to migration. Therefore, migration tasks are
    interspersed within sprints as needed. In addition only certain
    people can do specific tasks. Increase the man hours due to
    context switching; maybe add another 10 hours for inefficiency.

    TIME ESTIMATE
       Hours: 220
       Calendar Weeks: 14
       Delivery Date: circa July 2023

    CALCULATION
       Homogeneous task delivery is unrealistic, some weeks may need
       30 hours effort some 0. If you average 16 man hours effort a
       week you come up to 13.75 weeks. I rounded that up to 14 and
       figured 4 weeks per month from the start of March 2023 landing
       in July. That should smooth out deviations like vacation,
       illness, weekends, etc...


SHUTDOWN TFS ON PREMISE
    Our build systems are extensive. And our efforts to move away from
    on premise TFS has only got us to 60% in the last eight years.

    Without TFS we:
       Cannot archive official assets
       Cannot build SmartExporter desktop
       Cannot create private builds
       Cannot digitally sign assets
       Cannot run data tests
       Cannot send build notifications
       Cannot version control outside assets, e.g. documentation
       Missing bandwidth
       Missing storage Space (File Shares)

    These problems represent individual challenges, non of which are
    easy. So as of March 2023 I have no estimates and will amend my
    data when possible.


SPECIAL PROBLEMS
    There are additional special one-off problems not so easy to
    plan due to cross-cutting, dependencies and their relationships
    to uncontrollable circumstances. These special problems
    are addressed by themselves.

    SmartExporter Setup
        Upgrade Install Shield
        Migrate SmartExporter to x64 only
        Deliver .NET assets plus .NET Framework assets
        Manage third-party dependencies (SAP DLL VC RUNTIME)

    GitHub Private Runner
        Some on premise, some co-located
        Where? Canada? Azure? AwS? Cluj? Duesseldorf?
        Network Access? Firewall
        OS Maintainers?

    On premise TFS assets
        Migrate where? LFS? Google? NAS?
        Backups?
        Supply Chain Attacks?
        Version Control?
        Who has access?

    GitHub + Jira Integration
        Trial?
        Cost?
        Who manages?

    LFS Storage Configuration
       NuGet?
       Merge Module?
       Files For Build?
       Cost?
       Bandwidth?
       Backup?

JOURNAL
    We upgraded the SmartExporter organization to Team with 5 seats, one
    for each developer. Cost 220 per year.

    All core developers are in the organization.

    Started tracking migration issues via GitHub issues to maintaining
    an idea of what works, what does not, and improve planning.

    Prototype CI workflow
        We migrated se.readme to cwase.readme and created a prototype
        action workflow that lets us build a single NuGet package
        project and deploy said package to the GitHub package server.

        It's progress but sill has numerous bug and issues. We can not
        yet build meta-package projects, e.g. se.kernel until this
        is resolved.

    We manually migrated the majority of our NuGet packages by
    downloading them from Azure DevOps one by one and uploaded them
    with some script magic. We still need to verify if everything
    is present.

    We migrated se.test.transfers using a CI variation of cwase.readme
    and published it.

    We are actively using cwase.io as a CI prototype platform to
    finalize sing NuGet package builds. Once complete we can actively
    migrate about 60 other projects.

    Our Azure DevOps security model has no equal on GitHub. We
    have to throw out everything and start fresh. It took us
    roughly 40 hours on Azure DevOps the first time.
```



