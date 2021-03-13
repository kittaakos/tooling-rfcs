# Arduino Tooling-related RFCs

Most changes to Arduino tooling projects can be done simply by submitting a pull request for the proposed change and passing through the standard PR review process.

In the case of proposal for substantial changes, it may be beneficial to first document, discuss with stakeholders, and get formal approval before starting on the associated work. The "RFC" (request for comments) process is used for this purpose.

## Table of contents

<!-- toc -->

- [When the RFC process is required](#when-the-rfc-process-is-required)
  - [What is "tooling"?](#what-is-tooling)
- [RFC workflow](#rfc-workflow)
  - [1. Plan and research](#1-plan-and-research)
  - [2. Write](#2-write)
  - [3. Submit](#3-submit)
  - [4. Resolve CI failures](#4-resolve-ci-failures)
  - [5. Review and revision](#5-review-and-revision)
  - [6. Conclusion](#6-conclusion)

<!-- tocstop -->

## When the RFC process is required

RFCs might be required for proposals that have any of the following characteristics:

- Requires extensive changes to a project.
- Requires significant changes to multiple projects.
- Results in significant impacts on the users, especially breaking changes.
- Potentially controversial.

### What is "tooling"?

The scope of the RFCs in this repository is limited to Arduino's tooling projects. Tooling is the software components related to the development and deployment of Arduino firmware. Prominent examples include:

- [Arduino IDE](https://github.com/arduino/arduino-ide)
- [Arduino CLI](https://github.com/arduino/arduino-cli)
- [Arduino Create Agent](https://github.com/arduino/arduino-create-agent)
- [Arduino Language Server](https://github.com/arduino/arduino-language-server)
- [serial-discovery](https://github.com/arduino/serial-discovery)

## RFC workflow

### 1. Plan and research

First of all, check existing RFCs. There may already be one for your proposal, or related information to use as a reference.

- [Accepted RFCs](RFCs)
- [Pending and rejected RFCs](https://github.com/arduino/tooling-rfcs/pulls?q=is%3Apr+is%3Aclosed)

#### Resources

- Arduino build system docs: [hosted under the Arduino CLI docs website](https://arduino.github.io/arduino-cli/dev/)
- [Arduino development policy](https://github.com/arduino/Arduino/wiki/Development-Policy)

#### Discussion channels

- Talk with the user community on [the Arduino Forum](https://forum.arduino.cc/).
- Talk with Arduino developers on [the Arduino Developers Mailing List](https://groups.google.com/a/arduino.cc/forum/#!forum/developers).

### 2. Write

1. [Fork](https://help.github.com/en/github/getting-started-with-github/fork-a-repo) this repository.
1. Copy `0000-template.md` to `RFCs/0000-my-proposal.md` (replacing "my-proposal" with the RFC title). Don't assign an RFC number yet; this is going to be set according to the ID number GitHub assigns the pull request when it's submitted.
1. Fill in the RFC.
   - If the RFC document requires supplemental files (e.g., graphics), put them under the `RFCs/assets/0000-my-proposal` folder, where "0000-my-proposal" is the proposal file name.

#### Resources

- [Style Guide](https://tools.ietf.org/html/rfc7322)
- [Requirement levels key words](https://tools.ietf.org/html/rfc2119)
- [Writing guide](https://github.com/inasafe/inasafe/wiki/How-to-write-an-RFC)

### 3. Submit

1. Submit a [pull request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests) from your fork to add the RFC document.
1. Check which identifier number GitHub has assigned your pull request. This will be shown immediately after the pull request title, prefixed with `#`.
1. Rename the RFC file in your fork to use the pull request number, padding with zeros to make the number have four digits. For example, if the pull request number was `#42`, the RFC file should be renamed from `RFCs/0000-my-proposal.md` to `RFCs/0042-my-proposal.md`.
   - Note that any changes you make to the files in the branch of your fork the pull request was submitted from will automatically update the pull request.

### 4. Resolve CI failures

When the pull request is submitted, some automated checks will be done to make sure there are no problems. Once these checks are finished, you can see a summary of the results on the "Checks" tab of the pull request page. If any checks failed, please check the associated logs and fix whatever caused it to fail.

### 5. Review and revision

Interested parties should now review and discuss the RFC. This is done using GitHub's pull request review system:<br />
https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-request-reviews

In order to allow everyone the opportunity to comment, a minimum period of 14 days (starting from the submission of the pull request for review) is provided before merging or rejecting the RFC.

During this time, the RFC author and reviewers should work together to reach consensus and make necessary adjustments or improvements to the RFC. It's important for the RFC author to be responsive during the review period, so make sure to allocate some time for this during the review period before submitting the pull request.

#### Review

- Comments and discussion about specific lines should be done via [line comments](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request#adding-line-comments-to-a-pull-request).
- Requests for specific changes to the text should be done using GitHub's ["Suggestions" feature](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/reviewing-proposed-changes-in-a-pull-request#starting-a-review:~:text=Optionally%2C%20to%20suggest%20a%20specific%20change). This allows the RFC author to easily accept them via the GitHub web interface.
- General feedback and discussion can be done via the [review message](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/reviewing-proposed-changes-in-a-pull-request#submitting-your-review) or in [the pull request conversation thread](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request#about-pull-request-comments).
- General support for review or discussion comments can be indicated by using GitHub's ["Reactions" feature](https://github.blog/2016-03-10-add-reactions-to-pull-requests-issues-and-comments/) to give a :+1:, but note that this will not be considered a formal approval of the RFC. Although it is generally more constructive to provide detailed constructive criticism or suggestions for improvement, in cases where this would be redundant the "Reactions" feature can be used to give a :-1:.

#### Revision

The author can make revisions to the RFC in response to the reviews.

Note that any changes you make to the files in the branch of your fork the pull request was submitted from will automatically update the pull request so there is no need to open a new pull request for the modifications.

Although it is normally best practices, during the RFC review process the technique of doing a "squash" or "fixup" and force pushing to the PR branch to maintain an atomic commit history should not be done. The reason is because this makes it a little more difficult for reviewers to follow the revisions that have been made. The maintainer will squash the pull request to a single commit at the time of the merge.

If in agreement with a change requested via GitHub's "Suggestions" feature, simply [click the "Commit suggestion" button](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/incorporating-feedback-in-your-pull-request).

Once a review discussion has been resolved, [click the "Resolve conversation" button](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request#resolving-conversations) to clearly indicate this to all involved parties. This is done automatically for committed "suggestions".

### 6. Conclusion

#### Acceptance

The RFC may be accepted and the pull request merged if all the following conditions are met:

- 14 days have passed since the pull request was submitted for review.
- At least two members of the Arduino Tooling Team have approved the RFC via the GitHub pull request review system.
- There are no outstanding requests for changes from members of the Arduino Tooling Team.

#### Rejection

The RFC may be rejected and the pull request closed if all the following conditions are met:

- 14 days have passed without any activity on the pull request.
- The pull request has not been approved by any member of the Arduino Tooling Team via the GitHub pull request review system.
