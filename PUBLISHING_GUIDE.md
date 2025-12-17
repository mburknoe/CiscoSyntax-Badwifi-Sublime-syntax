# Publishing to Sublime Text Package Control

This guide outlines the steps to publish **CiscoSyntax BadWifi** to the official Sublime Text Package Control repository.

## Prerequisites

Before submitting your package, ensure you have:

- [x] A public GitHub repository
- [x] A valid `LICENSE` file (MIT ✅)
- [x] A comprehensive `README.md` (✅)
- [x] A working `.sublime-syntax` file (✅)
- [ ] (Optional) A `package.json` file for metadata
- [ ] (Optional) Screenshots demonstrating the syntax highlighting
- [ ] At least one tagged release on GitHub

---

## Step 1: Create a GitHub Release

1. **Tag your current version:**
   ```bash
   git tag -a v1.0.0 -m "Initial release of CiscoSyntax BadWifi"
   git push origin v1.0.0
   ```

2. **Create a release on GitHub:**
   - Go to your repository on GitHub
   - Click "Releases" → "Create a new release"
   - Select the `v1.0.0` tag
   - Add release notes describing features
   - Publish the release

---

## Step 2: Add Package Metadata (Optional but Recommended)

Create a `package.json` file in your repository root:

```json
{
  "name": "CiscoSyntax BadWifi",
  "description": "Comprehensive syntax highlighting for Cisco IOS, NX-OS, and IOS-XE configurations",
  "author": "Badwifi.dev",
  "homepage": "https://github.com/badwifi/CiscoSyntax-Badwifi-Sublime-syntax",
  "issues": "https://github.com/badwifi/CiscoSyntax-Badwifi-Sublime-syntax/issues",
  "license": "MIT",
  "keywords": ["cisco", "ios", "syntax", "highlighting", "network", "configuration"],
  "sublime_text": ">=3000"
}
```

---

## Step 3: Submit to Package Control

### Option A: Via GitHub Pull Request (Recommended)

1. **Fork the Package Control repository:**
   - Go to https://github.com/wbond/package_control_channel
   - Click "Fork" to create your own copy

2. **Clone your fork locally:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/package_control_channel.git
   cd package_control_channel
   ```

3. **Add your package to the repository listing:**
   - Open the `repository/c.json` file (packages starting with 'C')
   - Add your package entry in alphabetical order:

   ```json
   {
     "name": "CiscoSyntax BadWifi",
     "details": "https://github.com/badwifi/CiscoSyntax-Badwifi-Sublime-syntax",
     "releases": [
       {
         "sublime_text": ">=3000",
         "tags": true
       }
     ]
   }
   ```

4. **Commit and push your changes:**
   ```bash
   git checkout -b add-ciscosyntax-badwifi
   git add repository/c.json
   git commit -m "Add CiscoSyntax BadWifi package"
   git push origin add-ciscosyntax-badwifi
   ```

5. **Create a Pull Request:**
   - Go to your fork on GitHub
   - Click "Pull Request"
   - Ensure the base repository is `wbond/package_control_channel` and base branch is `master`
   - Provide a clear description of your package
   - Submit the PR

### Option B: Via Package Control Website (Alternative)

1. Visit https://packagecontrol.io/submit
2. Fill out the submission form with your package details
3. Submit for review

---

## Step 4: Wait for Review

- Package Control maintainers will review your submission
- They may request changes or improvements
- Review typically takes 1-7 days
- You'll be notified via GitHub when approved

---

## Step 5: Post-Approval

Once approved:

1. **Update your README:**
   - Change "Via Package Control (Coming Soon)" to just "Via Package Control"
   - Users can now install directly through Package Control

2. **Announce your package:**
   - Share on Reddit: r/SublimeText
   - Share on relevant Cisco/networking communities
   - Update your personal website or portfolio

---

## Maintaining Your Package

### Releasing Updates

1. Make changes to your code
2. Update version in any relevant files
3. Create a new git tag:
   ```bash
   git tag -a v1.1.0 -m "Add support for XYZ feature"
   git push origin v1.1.0
   ```
4. Package Control will automatically detect new tags and make them available

### Best Practices

- Follow [Semantic Versioning](https://semver.org/): `MAJOR.MINOR.PATCH`
- Keep your README updated
- Respond to issues and pull requests promptly
- Add a `CHANGELOG.md` to track version changes

---

## Additional Resources

- **Package Control Documentation**: https://packagecontrol.io/docs
- **Sublime Syntax Documentation**: https://www.sublimetext.com/docs/syntax.html
- **Package Control Channel Repo**: https://github.com/wbond/package_control_channel

---

## Troubleshooting

### Common Issues

**Package not showing up after approval:**
- Users need to restart Sublime Text
- Check that your repository is public
- Verify the syntax file has the correct structure

**Syntax not being applied:**
- Ensure `file_extensions` are correctly defined
- Check for syntax errors in the `.sublime-syntax` file
- Verify the `scope` is set properly

**Installation fails:**
- Check that your repository doesn't have large binary files
- Ensure all paths in documentation are correct
- Verify the package name matches exactly

---

## Quick Checklist

Before submitting to Package Control:

- [ ] Repository is public on GitHub
- [ ] LICENSE file exists (MIT)
- [ ] README.md is comprehensive and well-formatted
- [ ] At least one release tag exists (e.g., v1.0.0)
- [ ] Syntax file is tested and working
- [ ] (Optional) package.json added
- [ ] (Optional) Screenshots added to README
- [ ] Fork package_control_channel repository
- [ ] Add package entry to repository/c.json
- [ ] Submit Pull Request with clear description

---

Good luck with your submission! 🚀
