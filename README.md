# Mimo xdg-open

**mimo** is a (mimi)[https://github.com/march-linux/mimi] fork, an improved
version of xdg-open.


# Usage

* Define a configuration file: `'~/.config/mimo/mime.conf'`.

* mimo will search a best-fit app using .desktop file. Best fit is defined as
  the first option sorted by mime order and then, if they have the same mime
  order, reverse sorted by generality.

* mimo allows you to open multiple files at once if more than one parameter is
  provided.


# Configuration

Example `~/.config/mimo/mime.conf`:

    text/: xterm -e vim
    text/html: firefox
    application/pdf: zathura
    video/: mplayer
    image/: sxiv
    audio/: vlc
    application/x-tar: xterm -e 2a
    application/x-gzip: xterm -e 2a
    application/x-bzip2: xterm -e 2a
    application/x-rar: xterm -e 2a
    application/x-xz: xterm -e 2a
    application/zip: xterm -e 2a
    inode/directory: xterm -e ranger


# Search order

For a `'text/html'` example file:

1. 'txt'
2. <protocol>
3. 'text/html'
4. 'text/'
5. 'text/html' in `.desktop`
6. 'text/' in `.desktop`
7. Prompt the user
