ZipSlip Lab

An interactive, browser-based Zip Slip (Archive Path Traversal) demonstration tool built with pure JavaScript. 100% client-side, zero dependencies, and no server required.

Made by: Aryan Giri
GitHub: "@giriaryan694-a11y" (https://github.com/giriaryan694-a11y)

🔗 Live Demo: https://giriaryan694-a11y.github.io/ZipSlip-Lab/

What is Zip Slip?

Zip Slip is an archive extraction vulnerability publicly documented by Snyk in 2018. It occurs when an archive contains specially crafted entry names that can escape the intended extraction directory.

When an application extracts archive entries without properly validating their paths, files may be written outside the intended destination.

ZipSlip Lab provides an interactive environment to understand how these crafted archive entries are created and represented.

Features

Create ZIP

Create demonstration ZIP archives with custom entries:

- Specify file names and content using inline text or uploaded files.
- Configure the intended overwrite directory.
- Preview generated archive entries and their intended destinations.
- Add multiple files to a single archive.
- Customize the generated ZIP filename.
- Generate and download the archive.

Upload ZIP

Explore and inspect existing ZIP archives:

- Upload and parse existing ".zip" files.
- View archive entry names and paths.
- Examine crafted path-traversal entries.
- View the total number of archive entries.
- Inspect ZIP compression methods.

Additional Features

- Zero dependencies: ZIP writing and central-directory reading are implemented in pure JavaScript.
- Client-side processing: Archive creation and inspection happen locally in the browser.
- No backend: No server-side processing or file uploads.
- Themes: Dark, Light, and Eye-saver modes with cookie-based persistence.
- Responsive interface: Designed for desktop and mobile devices.

Usage

1. Open "index.html" locally or visit the "Live Demo" (https://giriaryan694-a11y.github.io/ZipSlip-Lab/).
2. Select one of the available modes:
   - Create ZIP: Build a demonstration archive.
   - Upload ZIP: Inspect an existing archive.
3. In Create ZIP mode, enter a filename, content, and overwrite directory.
4. Select Add file to include the entry.
5. Repeat to add additional files.
6. Select Generate & download ZIP to create your archive.
7. In Upload ZIP mode, select a ".zip" file to inspect its archive entries.

Technical Notes

- Generated archive entries use the uncompressed ZIP storage method (Method 0).
- The overwrite path represents a directory; the filename is appended to it.
- Archive creation and inspection are performed entirely in the browser.

Educational Purpose

ZipSlip Lab is designed for cybersecurity learners, developers, and security researchers who want to understand the structure and mechanics of the Zip Slip vulnerability.

It demonstrates how crafted archive paths can be represented inside ZIP files and why unsafe extraction logic can create security risks.

Important: This project is an educational demonstration environment, not a production vulnerability scanner or a secure archive extraction utility.

Use it only in isolated environments or on systems you own or are explicitly authorized to test.

Understanding the Mitigation

A secure archive extraction implementation should:

- Canonicalize the resolved destination path.
- Validate that each extracted entry remains inside the intended extraction directory.
- Reject entries that resolve outside the permitted destination.

License

Released under the "MIT License" (LICENSE).
