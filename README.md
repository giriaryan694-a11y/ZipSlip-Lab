# ZipSlip Lab

An educational archive path-traversal (Zip Slip) demonstration tool. **100% client-side, zero dependencies, and no server required.**

**Author:** Aryan Giri  
**GitHub:** [@giriaryan694-a11y](https://github.com/giriaryan694-a11y)

🔗 **Live Demo:** [https://giriaryan694-a11y.github.io/ZipSlip-Lab/](https://giriaryan694-a11y.github.io/ZipSlip-Lab/)

## What is Zip Slip?

Zip Slip is an archive extraction vulnerability publicly documented by Snyk in 2018. It occurs when an archive contains crafted entry paths that escape the intended extraction directory.

If an extractor does not properly validate archive entry paths, files may be written outside the intended destination. This can potentially lead to unauthorized file modification or code execution, depending on the affected application and environment.

## Features

### Create ZIP
Build demonstration archives file by file:

- Specify a file name and content using inline text or an uploaded file.
- Configure the intended overwrite directory.
- Automatically add a standard eight-level `../` traversal prefix for absolute overwrite paths.
- Preview generated archive entries and their intended destinations.
- Add multiple files and choose a ZIP filename before generating the archive.

### Upload ZIP
Analyze existing ZIP archives:

- Detect `../` path-traversal entries.
- Identify absolute paths.
- Display archive entry counts.
- Inspect compression methods.
- Review potentially dangerous archive entries.

### Additional Features

- **Zero dependencies:** ZIP writing and central-directory parsing are implemented in pure JavaScript.
- **Client-side processing:** Files are processed locally in the browser. Nothing is uploaded to a server.
- **Themes:** Dark, Light, and Eye-saver modes with cookie-based persistence.
- **Responsive design:** Supports desktop and mobile screens.

## Usage

1. Open `index.html` locally or access the [Live Demo](https://giriaryan694-a11y.github.io/ZipSlip-Lab/).
2. Choose **Create ZIP** or **Upload ZIP**.
3. In Create ZIP mode, enter a filename, content, and overwrite directory.
4. Select **Add file** to include the entry. Repeat to add more files.
5. Select **Generate & download ZIP** to create the demonstration archive.
6. In Upload ZIP mode, select a `.zip` file to analyze its entries.

## Technical Notes

- Generated archive entries use the **uncompressed ZIP method (Method 0)**.
- The overwrite path represents a directory. The specified filename is appended to it.
- Absolute overwrite paths receive a standard `../` × 8 traversal prefix automatically.
- All archive processing takes place inside the browser.

## Educational Purpose

ZipSlip Lab demonstrates a publicly documented vulnerability class to help developers and security learners understand archive path-traversal risks.

Use this tool only in isolated environments or on systems you own or are explicitly authorized to test.

**Recommended mitigation:** Canonicalize each resolved extraction path and reject archive entries whose resolved destination falls outside the intended extraction directory.

## License

Released under the [MIT License](LICENSE).
