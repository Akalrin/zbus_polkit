# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## 6.0.0 - 2026-10-20

### 💥 Breaking
- Make AuthorityFeatures a bitflags type.
- Make CheckAuthorizationFlags a bitflags type.
- Pass a pidfd from Subject::new_for_owner. #103
- Rename the PID-based Subject::new_for_owner to Subject::new_for_pid.
- Hide the fields of Subject. Its kind is available through Subject::kind.
- Drop AuthorityProxyBlocking and the blocking-api feature, since zbus 6 has no blocking API.
- Port to zbus 6, where zbus::zvariant::Value is now zbus::Variant. This changes the type of
  Identity::identity_details and of the options argument of
  AuthorityProxy::register_authentication_agent_with_options.
- Raise the MSRV to 1.89.

### 👷 CI
- Install polkit in the test jobs.
- Sync renovate config with zbus.
- Add semver-checks job.
- Add doc build job.
- Test every feature combination.
- Run clippy on stable across the feature matrix.
- Add MSRV job and declare the real minimum Rust version.
- Pass --locked to all cargo invocations.
- Align CI workflow layout with zbus.
- Enforce gimoji commit messages.

### ♻️ Changed
- Move Subject into its own module.
- Split /proc parsing out of the file reads.
- Add git hook scripts from zbus.
- Add codespell config.
- Add .editorconfig.
- Add rustfmt config matching zbus.
- Configure release-plz.

### 📦 Dependencies
- Use zbus 6.0.0 from crates.io.
- Update tokio to v1.53.3.
- Update zbus to its latest git main.
- Update serde_json to v1.0.154 (#116).
- Update serde_json to v1.0.152 (#115).
- Update zbus to its latest git main.
- Drop the enumflags2 dependency.
- Add the bitflags dependency.
- Update tokio to v1.53.2 (#112).
- Bump MSRV to match with the new zbus MSRV.
- Add rustix as a dev-dependency.
- Add serde_json as a dev-dependency.
- Depend on zbus git main and bump to 6.0.0.

### 📝 Documentation
- Show a pidfd in the README example.
- Document the Authority test backends.
- Document the git hook scripts.
- Add pull request template.
- Add security policy.
- Point CI badge at zbus_polkit.
- Add contribution guide.

### 🐛 Fixed
- Name the /proc field that was missing.

### ⚙️ Other
- 👽️ Update to latest zbus.
- ✏️ Fix typo in RegisterAuthenticationAgentWithOptions docs.

### ✅ Testing
- Drive AuthorityProxy against real or mock polkit.
- Test system-bus-name subjects from message headers.
- Test polkit wire signatures and enum encoding.
- Test unix-process subjects and /proc parsing.
