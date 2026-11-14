
# CCD_HACKBOX Release Checklist

Use this checklist before publishing a new CCD_HACKBOX release.

## 1. Project Verification

- [ ] Confirm the target VM boots successfully.
- [ ] Confirm the target hostname.
- [ ] Confirm network configuration.
- [ ] Confirm the intended challenge directories exist.
- [ ] Review challenge permissions and configurations.
- [ ] Test each challenge independently.
- [ ] Confirm reset or recovery procedures.

## 2. Documentation

- [ ] Update the main README.
- [ ] Update CHANGELOG.
- [ ] Review the lab guide.
- [ ] Review network setup instructions.
- [ ] Update troubleshooting documentation.
- [ ] Document known limitations.
- [ ] Confirm version information is accurate.

## 3. Public Repository Security

- [ ] Review all files staged for publication.
- [ ] Exclude instructor walkthroughs.
- [ ] Exclude private flags and credentials.
- [ ] Exclude private keys and tokens.
- [ ] Review scripts for unsafe behavior.
- [ ] Review Git history for previously committed secrets.
- [ ] Confirm that public documentation does not expose private challenge solutions.

Important: Adding a file to .gitignore does not remove it from Git history or stop tracking an already committed file.

## 4. OVA Preparation

- [ ] Create a separate student distribution copy.
- [ ] Remove instructor-only materials from that copy.
- [ ] Confirm that no private credentials or flags are exposed.
- [ ] Configure the VM for safe first-time startup.
- [ ] Confirm the recommended network mode.
- [ ] Export the student VM as an OVA.
- [ ] Test importing the OVA on a separate VirtualBox environment.
- [ ] Verify that the imported VM boots and the documented exercises work.

Do not export the original development VM without first reviewing its contents.

## 5. GitHub Release

- [ ] Confirm the repository documentation is current.
- [ ] Create a version tag.
- [ ] Prepare release notes.
- [ ] Upload the tested OVA as a release asset.
- [ ] Include checksums for the published artifact.
- [ ] Verify that the release asset can be downloaded and imported.

## 6. Release Status

A release should only be marked ready after the checks above have been completed.

Do not describe an OVA as available until it has been exported, tested and published.
