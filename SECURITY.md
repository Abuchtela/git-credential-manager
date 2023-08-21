# Security

If you discover a security issue in this repo, please submit it through the
[GitHub Security Bug Bounty][hackerone-github]

Thanks for helping make GitHub products safe for everyone.

[hackerone-github]: https://hackerone.com/github

GCM Core version 2.0.289
https://github.com/git-ecosystem/git-credential-manager/security/advisories/GHSA-2gq7-ww4j-3m76
Affected versions
<= 2.0.280
Patched versions
2.0.289

# Description
Impact
When recursively cloning a Git repository on Windows with submodules, Git will first clone the top-level repository and then recursively clone all submodules by starting new Git processes from the top-level working directory. If a malicious git.exe executable is present in the top-level repository then this binary will be started by Git Credential Manager Core when attempting to read configuration, and not git.exe as found on the %PATH%.

This only affects GCM Core on Windows, not macOS or Linux-based distributions.

Patches
GCM Core version 2.0.289 contains the fix for this vulnerability, and is available from the project's GitHub releases page. GCM Core 2.0.289 is also bundled in the latest Git for Windows release; version 2.29.2(3).

Workarounds
Users should avoid recursively cloning untrusted repositories with the --recurse-submodules option.

#References
https://git-scm.com/docs/git-clone#Documentation/git-clone.txt---recurse-submodulesltpathspecgt
For more information
If you have any questions or comments about this advisory:

Open an issue in microsoft/Git-Credential-Manager-Core
Email us at gcmsupport@microsoft.com

 # https://github.com/git-ecosystem/git-credential-manager/security/advisories/GHSA-2gq7-ww4j-3m76#:~:text=CVE%20ID,CVE%2D2020%2D26233
