---
Dip: <to be assigned>
title: <DIP title>
author: <a list of the author's or authors' name(s) and/or username(s), or name(s) and email(s), e.g. (use with the parentheses or triangular brackets): FirstName LastName (@GitHubUsername), FirstName LastName <foo@bar.com>, FirstName (@GitHubUsername) and GitHubUsername (@GitHubUsername)>
status: Draft
type: <DRC, Core, Interface, or Networking>
created: <date created on, in ISO 8601 (yyyy-mm-dd) format>
requires (*optional): <DIP number(s)>
replaces (*optional): <DIP number(s)>
---

This is the suggested template for new DIPs.

Note that a DIP number will be assigned by an editor. When opening a pull request to submit your DIP, please use an abbreviated title in the filename, `Dip-draft_title_abbrev.md`.

The title should be 44 characters or less.

## Summary
"If you can't explain it simply, you don't understand it well enough." Provide a simplified and layman-accessible explanation of the DIP. Imagine an email subject line, GitHub PR title, or forum post title.

## Motivation
The motivation section should describe the "why" of this DIP. What problem does it solve? Why should someone want to implement this standard? What benefit does it provide to the Ethereum ecosystem? What use cases does this DIP address?

## Specification
The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Ethereum platforms (go-ethereum, parity, cpp-ethereum, ethereumj, ethereumjs, and [others](https://github.com/ethereum/wiki/wiki/Clients)).

## Rationale
The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages.

## Backwards Compatibility
All DIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The DIP must explain how the author proposes to deal with these incompatibilities. DIP submissions without a sufficient backwards compatibility treatise may be rejected outright.

## Test Cases
Test cases for an implementation are mandatory for DIPs that are affecting consensus changes. Other DIPs can choose to include links to test cases if applicable.

## Reference Implementation
An optional section that contains a reference/example implementation that people can use to assist in understanding or implementing this specification.  If the implementation is too large to reasonably be included inline, then consider adding it as one or more files in `../assets/Dip-####/`.

## Security Considerations
All DIPs must contain a section that discusses the security implications/considerations relevant to the proposed change. Include information that might be important for security discussions, surfaces risks and can be used throughout the life cycle of the proposal. E.g. include security-relevant design decisions, concerns, important discussions, implementation-specific guidance and pitfalls, an outline of threats and risks and how they are being addressed. DIP submissions missing the "Security Considerations" section will be rejected. A DIP cannot proceed to status "Final" without a Security Considerations discussion deemed sufficient by the reviewers.

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
