# ZipSlip Lab

An interactive, browser-based **Zip Slip (Archive Path Traversal) demonstration and ZIP archive analysis tool** built with pure JavaScript. 100% client-side, zero dependencies, and no server required.

**Made by:** Aryan Giri  
**GitHub:** [@giriaryan694-a11y](https://github.com/giriaryan694-a11y)

🔗 **Live Demo:** https://giriaryan694-a11y.github.io/ZipSlip-Lab/

## What is Zip Slip?

Zip Slip is an archive extraction vulnerability publicly documented by Snyk in 2018. It occurs when an archive contains specially crafted entry names that can escape the intended extraction directory.

When an application extracts archive entries without properly validating their paths, files may be written outside the intended destination.

ZipSlip Lab provides an interactive environment to create, inspect, and analyze ZIP archives to understand how this vulnerability works.

## Features

### Create ZIP

- Create demonstration ZIP archives with custom entries.
- Specify file names and content using inline text or uploaded files.
- Configure overwrite directories.
- Preview generated archive entries and their intended destinations.
- Add multiple files to a single archive.
- Customize the generated ZIP filename.
- Generate and download archives.

### Upload & Analyze ZIP

- Upload and parse existing `.zip` archives.
- Inspect archive entry names and paths.
- Examine path-traversal patterns.
- View archive entry counts.
- Inspect ZIP compression methods.
- Analyze archive structure directly in the browser.

### Additional Features

- **Zero dependencies:** ZIP writing and central-directory reading are implemented in pure JavaScript.
- **Client-side processing:** Archive creation and analysis happen locally in the browser.
- **No backend:** No server-side processing or file uploads.
- **Themes:** Dark, Light, and Eye-saver modes with cookie-based persistence.
- **Responsive interface:** Supports desktop and mobile devices.

## Usage

1. Open `index.html` locally or visit the [Live Demo](https://giriaryan694-a11y.github.io/ZipSlip-Lab/).
2. Choose **Create ZIP** or **Upload ZIP**.
3. Create mode: configure archive entries and generate a ZIP file.
4. Upload mode: select an existing `.zip` file to inspect and analyze its contents.

## Technical Notes

- Generated archive entries use the uncompressed ZIP storage method (Method 0).
- The overwrite path represents a directory; the filename is appended to it.
- Archive creation and analysis are performed entirely in the browser.

## Educational Purpose

ZipSlip Lab is designed for cybersecurity learners, developers, and security researchers interested in archive path-traversal vulnerabilities.

It demonstrates how crafted archive paths are constructed and represented inside ZIP files, while providing tools to inspect and analyze archive contents.

**Important:** This is an educational demonstration and archive analysis tool, not a production-grade secure extraction utility.

Use it only in isolated environments or on systems you own or are explicitly authorized to test.

### Understanding the Mitigation

Secure archive extraction should:

- Canonicalize resolved destination paths.
- Ensure extracted entries remain inside the intended extraction directory.
- Reject entries that resolve outside the permitted destination.

## License

Released under the [MIT License](LICENSE).
