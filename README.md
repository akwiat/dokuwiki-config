# Dokuwiki Setup
 * Config mac for localhost server to test out the wiki: https://discussions.apple.com/docs/DOC-11238
 * Download and install dokuwiki https://www.dokuwiki.org/install
 * install the latex plugin https://www.dokuwiki.org/plugin:latex
  * Also install the dependencies:
  * Install basictex: http://www.tug.org/mactex/morepackages.html
  * `brew install ghostscript`
  * `brew install imagemagick --with-ghostscript`
  * Modify the `class.latexrender.php` file inside the plugin to include the line: `putenv("PATH=/usr/local/bin")` before the `convert` command. (I put it in line 246) This is necessary because the imagemagick `convert` command called by the php script in the latex plugin needs access to ghostscript (which is located at `/usr/local/bin/gs` on my system).
  * In the wiki, navigate to Admin -> Configuration Settings and scroll down to the latex plugin. 
