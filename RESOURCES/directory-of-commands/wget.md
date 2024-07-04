#os/linux/commands/manuals/wget

# Download only files from the website using wget

Wget is a powerful command-line utility that allows you to download files from a website. Here are some basic examples of how to use wget to download files from a website:

## Example 1: Download a Single File**

To download a single file from a website, use the following command:

```bash
wget <url_of_file>
```

Replace `<url_of_file>` with the URL of the file you want to download.

## **Example 2: Download Multiple Files**

To download multiple files from a website, use the following command:

```bash
wget -r <url_of_directory>
```

Replace `<url_of_directory>` with the URL of the directory containing the files you want to download.

## Example 3: Download Files with Specific Extensions**

To download files with specific extensions, use the following command:

```bash
wget -A <extension> <url_of_directory>
```

Replace `<extension>` with the extension of the files you want to download (e.g., `.pdf`, `.zip`, etc.) and `<url_of_directory>` with the URL of the directory containing the files.

## Example 4: Download Files with Specific Names**wq

To download files with specific names, use the following command:

```bash
wget -w <filename> <url_of_directory>
```

Replace `<filename>` with the name of the file you want to download and `<url_of_directory>` with the URL of the directory containing the file.

## Example 5: Download Files Recursively**

To download files recursively from a website, use the following command:

```bash
wget -r -l <level> <url_of_directory>
```

Replace `<level>` with the level of recursion you want to use (e.g., 1, 2, etc.) and `<url_of_directory>` with the URL of the directory containing the files.

## **Example 6: Download Files with Authentication**

To download files from a website that requires authentication, use the following command:

```bash
wget -U <username> -p <password> <url_of_file>
```

Replace `<username>` with your username and `<password>` with your password.

**Additional Options**

Here are some additional options you can use with wget:

- `-O` : Specify the output file name.
- `-P` : Specify the download directory.
- `-k` : Keep the original file names.
- `-c` : Continue downloading a partially downloaded file.
- `-b` : Background download.
- `-t` : Set the timeout for the download.

## **Example 7: Download Files with Custom Options**

To download files with custom options, use the following command:

```bash
wget -O <output_file> -P <download_directory> -k -c -b -t 10 <url_of_file>
```

Replace `<output_file>` with the output file name, `<download_directory>` with the download directory, and `<url_of_file>` with the URL of the file you want to download.

Remember to replace the placeholders with the actual values and adjust the options according to your needs.