# Tools for doing code reviews

April 2016

I did a quick survey of tools for supporting the code review process, with a
focus on tools that integrate with GitHub. Since this is likely to become
outdated again fairly quickly, I'll not turn this into an extensive document,
but as a set of notes it may still be useful to those wanting to give this a
try.

- SmartBear Collaborator (http://smartbear.com/collaborator)
  - License: proprietary, runs on your own server
  - Workflow:
    - Submit code from SCM to Collaborator for review
    - Reviewers review code and enter comments
    - Author fixes issues
    - Roles: Reviewer, Moderator, Author
    - Review pools
    - Create custom checklists
    - Review documents (user stories, test plans)
  - Github: pull request support, creates a link to external review

- Klocwork (http://www.klocwork.com/Code-Review-Tools)
  - Link dead, doesn't appear to offer any code review tools

- Jetbrains Upsource (http://www.jetbrains.com/upsource/)
  - License: proprietary, runs on your own server or cloud
  - Integrates with JetBrains IDEs (PyCharm, IntelliJ)
  - No Github integration?

- Reviewable (http://reviewable.io)
  - Free for public and personal repos, hosted?
  - 10 users private repos for $39/month
  - Heavily integrated with Github

- ReviewNinja (http://www.review.ninja)
  - AL2.0, hosted at SAP for free, or hosted locally
  - Heavily integrated with Github
  - Approve changes, or flag a problem
  - Looks a bit less highly developed than Reviewable, maybe not much better than bare Github

- Gerrit Code Review (http://gerrithub.io)
  - AL2.0 and other FOSS, hosted locally
  - Need to submit to Gerrit, forwards changes to Github, which will become read-only
  - Submit changes through git protocol (i.e. command line tool or IDE integration)
  - Web interface for reviews

- Barkeep (http://getbarkeep.org)
  - MIT license, hosted locally
  - Made by Ooyala

- Codebrag (http://codebrag.com)
  - AGPLv3, hosted locally
  - Gets updates from repository, offers them up for review, mails reviewers
  - Does not integrate with Github Pull Requests

- Review Board (http://reviewboard.org)
  - Permissive open source, $10/user/month with Github Enterprise, $29/month with hosting
    - free for open source and educational use
  - Issue tracking for comments
  - Moved code detection
  - File attachment review
  - Multi-line commenting
  - No integration with pull requests yet

- Stash (Atlassian) -> Bitbucket Server
  - Not Github?

- JIRA
  - Commercial development environment

- CodeReviewHub (https://www.codereviewhub.com)
  - Hosted online, free (but for how long)
  - Heavily integrated with Github
  - CodeReviewHub automatically adds a task list in every pull requests description. Every
comment a reviewer makes in a pull request gets added as a task for the developer. The
developer then works through all these tasks, fixes them and marks them as completed.
After this the reviewer comes back and either approves the pull request or adds new items to
the task list by writing new comments.

- Gitmate (http://gitmate.io)
  - Workflow automation
    - Triage issues
    - Review code (actually, static analysis using coala)
    - Coordinate reviews and pull requests
  - Beta, not entirely clear if it does code review support and how


