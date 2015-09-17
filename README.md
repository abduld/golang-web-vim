[中文版说明](README_CN.md)

# go-vim Docker image
This Docker image adds [Go](https://golang.org/) tools and the following vim plugins to the [official Go image](https://registry.hub.docker.com/_/golang/):

when use screen, don't forget to use 256 colors. By default, screen use an 8-color terminal emulator.
To enable 256 colors, you need to edit ~/.screenrc
```
attrcolor b ".I"   
termcapinfo xterm 'Co#256:AB=\E[48;5;%dm:AF=\E[38;5;%dm'   
defbce on    
```
for more information pls visit [use 256 colors in screen](https://wiki.archlinux.org/index.php/GNU_Screen)

* [delimitMate](https://github.com/Raimondi/delimitMate) provides automatic closing of quotes, parenthesis, brackets, etc.
* [neocomplete](https://github.com/Shougo/neocomplete.vim) auto completion.  It provides keyword completion system by maintaining a cache of keywords in the current buffer
* [gitgutter](https://github.com/airblade/vim-gitgutter) shows a git diff in the gutter (sign column) and stages/reverts hunks.
* [colors-solarized](https://github.com/altercation/vim-colors-solarized) color scheme--solarized
* [airline](https://github.com/bling/vim-airline) lean & mean status/tabline for vim that's light as air
* [scala](https://github.com/derekwyatt/vim-scala)  a "bundle" for Vim that builds off of the initial Scala plugin
* [easymotion](https://github.com/easymotion/vim-easymotion) EasyMotion provides a much simpler way to use some motions in vim.
* [json](https://github.com/elzr/vim-json) A better JSON for Vim: distinct highlighting of keywords vs values, JSON-specific (non-JS) warnings, quote concealing. Pathogen-friendly.
* [go](https://github.com/fatih/vim-go) Go development plugin for Vim
* [snipmate](https://github.com/garbas/vim-snipmate) provide support for textual snippets, similar to TextMate or other Vim plugins like UltiSnips.
* [Vundle](https://github.com/gmarik/Vundle.vim) plugin manager for vim.
* [tabular](https://github.com/godlygeek/tabular) Aligning text
* [less](https://github.com/groenewege/vim-less) syntax highlighting, indenting and autocompletion for the dynamic stylesheet language `LESS`.
* [snippets](https://github.com/honza/vim-snippets) snipMate & UltiSnip Snippets
* [nerdtree-tabs](https://github.com/jistr/vim-nerdtree-tabs) NERDTree and tabs together in Vim, painlessly
* [bufexplorer](https://github.com/jlanzarotta/bufexplorer) BufExplorer Plugin for Vim
* [ctrlp](https://github.com/kien/ctrlp.vim) Fuzzy file, buffer, mru, tag, etc finder.
* [tagbar](https://github.com/majutsushi/tagbar) Vim plugin that displays tags in a window, ordered by scope http://majutsushi.github.com/tagbar/
* [addon-mw-utils](https://github.com/marcweber/vim-addon-mw-utils) interpret a file by function and cache file automatically(required by snipmate)
* [undotree](https://github.com/mbbill/undotree) The ultimate undo history visualizer for VIM
* [indent-object](https://github.com/michaeljsmith/vim-indent-object) This plugin defines a new text object, based on indentation levels.
* [indent-guides](https://github.com/nathanaelkane/vim-indent-guides) Indent Guides is a plugin for visually displaying indent levels in Vim.
* [html5](https://github.com/othree/html5.vim) HTML5 omnicomplete and syntax 
* [javascript](https://github.com/pangloss/vim-javascript) JavaScript bundle for vim, this bundle provides syntax and indent plugins.
* [markdown](https://github.com/plasticboy/vim-markdown) Markdown Vim Mode 
* [nerdcommenter](https://github.com/scrooloose/nerdcommenter) Vim plugin for intensely orgasmic commenting
* [nerdtree](https://github.com/scrooloose/nerdtree) A tree explorer plugin for vim.
* [syntastic](https://github.com/scrooloose/syntastic) Syntax checking hacks for vim
* [expand-region](https://github.com/terryma/vim-expand-region) visually select increasingly larger regions of text using the same key combination.
* [multiple-cursors](https://github.com/terryma/vim-multiple-cursors) True Sublime Text style multiple selections for Vim
* [tlib](https://github.com/tomtom/tlib_vim) (required by snipmatge)
* [fugitive](https://github.com/tpope/vim-fugitive)
* [haml](https://github.com/tpope/vim-haml)
* [repeat](https://github.com/tpope/vim-repeat)
* [surround](https://github.com/tpope/vim-surround)
* [EasyGrep](https://github.com/vim-scripts/EasyGrep)
* [YankRing](https://github.com/vim-scripts/YankRing.vim)
* [mru](https://github.com/vim-scripts/mru.vim)
* [taglist](https://github.com/vim-scripts/taglist.vim)

## Usage

Run this image from within your go workspace. You can than edit your project using `vim`, and usual go commands: `go build`, `go run`, etc. 

```
cd your/go/workspace
docker run --rm -tiv `pwd`:/go any35/golang-web-vim
```
 add `--privileged` flag debugger is needed
 
## Plugin Details
TBD.
### delimitMate
`shift+tab` jump to next autocomplete chart

### neocomplete
![Vim completion with animation.](https://f.cloud.github.com/assets/214488/623496/94ed19a2-cf68-11e2-8d33-3aad8a39d7c1.gif)

### gitgutter
![show git diff status in file](http://ww1.sinaimg.cn/large/69d56e38gw1efni76kr62j20po0os78b.jpg)

### colors-solarized
Modify .vimrc
```
syntax enable
set background=dark
colorscheme solarized
```
or
```
syntax enable
set background=light
colorscheme solarized
```

### easymotion
=====

	<cursor>Lorem ipsum dolor sit amet.

Type `<Leader><Leader>w`(`<Plug>(easymotion-w)`) to trigger the word motion `w`.
When the motion is triggered, the text is updated (no braces are actually added,
the text is highlighted in red by default):

	<cursor>Lorem {a}psum {b}olor {c}it {d}met.

Press `c` to jump to the beginning of the word "sit":

	Lorem ipsum dolor <cursor>sit amet.

Similarly, if you're looking for an "o", you can use the `f` motion.
Type `<Leader><Leader>fo`, and all "o" characters are highlighted:

	<cursor>L{a}rem ipsum d{b}l{c}r sit amet.

Press `b` to jump to the second "o":

	Lorem ipsum d<cursor>olor sit amet.

Jeffrey Way of Nettuts+ has also [written
a tutorial](http://net.tutsplus.com/tutorials/other/vim-essential-plugin-easymotion/)
about EasyMotion.

### json

### snipMate
For example, in C, typing `for<tab>` could be expanded to

    for (i = 0; i < count; i++) {
        /* code */
    }

with successive presses of tab jumping around the snippet.

in go, type `fun<tab>` could be expanded to 
```
    func funcName() error {
    
    }
```

for more snippets in golang pls see [go.snippets](https://github.com/honza/vim-snippets/blob/master/snippets/go.snippets)
and [more snippets](https://github.com/honza/vim-snippets/tree/master/snippets)

### fencview
this plugin auto detect CJK and Unicode file encodings. 
` :FencAutoDectect ` or ` :FencView `
and you can select the right encodings.

### tabular
#### Aligning assignments
Before:
```
one = 1
two = 2
three = 3
four = 4
```
Running `:Tab /=` produces
```
one   = 1
two   = 2
three = 3
four  = 4
```
#### Colon assignments
There are a couple of different ways that colon assignments could be aligned. If we start with an example that is not aligned:
```
var video = {
    metadata: {
        title: "Aligning assignments"
        h264Src: "/media/alignment.mov",
        oggSrc: "/media/alignment.ogv"
        posterSrc: "/media/alignment.png"
        duration: 320,
    }
}
````
Select the inner block by positioning your cursor inside it and running `vi}` (enable Visual mode, and select inner Brace). Then you could run `:Tab/:` which would produce this result:var 
```
video = {
    metadata: {
        title     : "Aligning assignments"
        h264Src   : "/media/alignment.mov",
        oggSrc    : "/media/alignment.ogv"
        posterSrc : "/media/alignment.png"
        duration  : 320,
    }
}
```
If you don’t like stacking the colons in a column, you could use the `\zs` atom to exclude the `:` character from the search match. Running `:Tab /:\zs` produces this result:
```
var video = {
    metadata: {
        title:      "Aligning assignments"
        h264Src:    "/media/alignment.mov",
        oggSrc:     "/media/alignment.ogv"
        posterSrc:  "/media/alignment.png"
        duration:   320,
    }
}
```
Be aware that if you work in a team, there may be a house style that you should follow.

#### Table markup
Here is a scenario outline for cucumber steps, including a pipe-delimited table of examples:
```
Scenario Outline: eating
  Given there are &lt;start&gt; cucumbers
  When I eat &lt;eat&gt; cucumbers
  Then I should have &lt;left&gt; cucumbers

  Examples:
    |start|eat|left|
    |12|5|7|
    |20|5|15|
```
With the cursor positioned anywhere in the table, running `:Tab/|` produces:
```
Scenario Outline: eating
  Given there are &lt;start&gt; cucumbers
  When I eat &lt;eat&gt; cucumbers
  Then I should have &lt;left&gt; cucumbers

  Examples:
    | start | eat | left |
    | 12    | 5   | 7    |
    | 20    | 5   | 15   |
```
see [tabular](http://vimcasts.org/episodes/aligning-text-with-tabular-vim/) for more information.
See [doc/Tabular.txt](http://raw.github.com/godlygeek/tabular/master/doc/Tabular.txt) for detailed documentation.

### vimless

### nerdtree-tabs
`F7` nerdTreeTabs toggle

i### buf explorer
`F4` open BufExplorer
`<Leader>be` BufExplorer 
after open buf explorer windows, 
`j` or `k` to choose file, `r` re-order files, `d` or `D` close fiel.

### CtrlP.vim
* Run `F6` or `:CtrlP` or `:CtrlP [starting-directory]` to invoke CtrlP in find file mode.
* Run `:CtrlPBuffer` or `:CtrlPMRU` to invoke CtrlP in find buffer or find MRU file mode.
* Run `:CtrlPMixed` to search in Files, Buffers and MRU files at the same time.

Check `:help ctrlp-commands` and `:help ctrlp-extensions` for other commands.

#### Once CtrlP is open:
* Press `<F6>` to purge the cache for the current directory to get new files, remove deleted files and apply new ignore options.
* Press `<c-f>` and `<c-b>` to cycle between modes.
* Press `<c-d>` to switch to filename only search instead of full path.
* Press `<c-r>` to switch to regexp mode.
* Use `<c-j>`, `<c-k>` or the arrow keys to navigate the result list.
* Use `<c-t>` or `<c-v>`, `<c-x>` to open the selected entry in a new tab or in a new split.
* Use `<c-n>`, `<c-p>` to select the next/previous string in the prompt's history.
* Use `<c-y>` to create a new file and its parent directories.
* Use `<c-z>` to mark/unmark multiple files and `<c-o>` to open them.

Run `:help ctrlp-mappings` or submit `?` in CtrlP for more mapping help.

* Submit two or more dots `..` to go up the directory tree by one or multiple levels.
* End the input string with a colon `:` followed by a command to execute it on the opening file(s):  
Use `:25` to jump to line 25.  
Use `:diffthis` when opening multiple files to run `:diffthis` on the first 4 files.

### Tagbar
`F8` TagbarToggle

### UndoTree
`F5` UndotreeToggle

### indent object
This plugin defines two new text objects. These are very similar - they differ
only in whether they include the line below the block or not.

        Key Mapping       Description     ~
===
        `<count>ai`         (A)n (I)ndentation level and line above.
        `<count>ii`         (I)nner (I)ndentation level (no line above).
        `<count>aI`         (A)n (I)ndentation level and lines above/below.
        `<count>iI`         (I)nner (I)ndentation level (no lines above/below).


Note that the iI mapping is mostly included simply for completeness, it is
effectively a synonym for ii.

Just like regular text objects, these mappings can be used either with
operators expecting a motion, such as 'd' or 'c', as well as in visual mode.
In visual mode the mapping can be repeated, which has the effect of
iteratively increasing the scope of indentation block selected. Specifying a
count can be used to achieve the same effect.

The difference between |ai| and |aI| is that |ai| includes the line
immediately above the indentation block, whereas aI includes not only that,
but also the line below. Which of these is most useful largely depends on the
structure of the language being edited.

For example, when editing the Python code, |ai| is generally more useful, as
the line above the indentation block is usually related to it. For example, in
the following code ( * is used to indicate the cursor position):
```
      if foo > 3:
         log("foo is big") *
         foo = 3
      do_something_else()
```
the if clause is logically related to the code block, whereas the function
call below is not. It is unlikely we would want to select the line below when
we are interested in the if block.

However, in other languages, such as Vim scripts, control structures are
usually terminated with something like 'endif'. Therefore, in this example:
```
      if foo > 3
         echo "foo is big" *
         let foo = 3
      endif
      call do_something_else()
```
we would more likely want to include the endif when we select the if
structure.
for example( * is used to indicate the cursor position)
```
aaaaaaaaaaaaa
    bbbbbbbbb*
    ccccccccc
        ddddddddd
eeeeeeeeeeeee
```
in normal model, when we execute 
* `>ai` it become
```
	aaaaaaaaaaaaa                                                                                                                        
		bbbbbbbbb*
		ccccccccc
			ddddddddd
eeeeeeeeeeeee
```
* `>ii` it cecome
````
aaaaaaaaaaaaa                                                                                                                        
		bbbbbbbbb*
		ccccccccc
			ddddddddd
eeeeeeeeeeeee
````
* `>aI` it cecome
````
	aaaaaaaaaaaaa                                                                                                                        
		bbbbbbbbb*
		ccccccccc
			ddddddddd
	eeeeeeeeeeeee
````
* `>iI` it cecome
````
aaaaaaaaaaaaa                                                                                                                        
		bbbbbbbbb*
		ccccccccc
			ddddddddd
eeeeeeeeeeeee
````

[document is here](https://github.com/michaeljsmith/vim-indent-object/blob/master/doc/indent-object.txt)

### indent guides
`<leader>ig` to switch indent guides display

### javascript.vim
`=G` auto indent
  NOTE: jquery syntax is not worked yet!

### nerdcommenter
The following key mappings are provided by default (there is also a menu 
provided that contains menu items corresponding to all the below mappings): 

Most of the following mappings are for normal/visual mode only. The |NERDComInsertComment| mapping is for insert mode only. 

**`[count]\<leader\>cc` |NERDComComment|**  
Comment out the current line or text selected in visual mode. 


**`[count]\<leader\>cn` |NERDComNestedComment|**  
Same as \<leader\>cc but forces nesting. 


**`[count]\<leader\>c<space>` |NERDComToggleComment|**  
Toggles the comment state of the selected line(s). If the topmost selected 
line is commented, all selected lines are uncommented and vice versa. 


**`[count]\<leader\>cm` |NERDComMinimalComment|**  
Comments the given lines using only one set of multipart delimiters. 


**`[count]\<leader\>ci` |NERDComInvertComment|**  
Toggles the comment state of the selected line(s) individually. 


**`[count]\<leader\>cs` |NERDComSexyComment|**  
Comments out the selected lines ``sexily'' 


**`[count]\<leader\>cy` |NERDComYankComment|**  
Same as \<leader\>cc except that the commented line(s) are yanked first. 


**`\<leader\>c$` |NERDComEOLComment|**  
Comments the current line from the cursor to the end of line. 


**`\<leader\>cA` |NERDComAppendComment|**  
Adds comment delimiters to the end of line and goes into insert mode between 
them. 


**|NERDComInsertComment|**  
Adds comment delimiters at the current cursor position and inserts between. 
Disabled by default. 


**`\<leader\>ca` |NERDComAltDelim|**  
Switches to the alternative set of delimiters. 


**`[count]\<leader\>cl`**  
**`[count]\<leader\>cb`    |NERDComAlignedComment|**  
Same as |NERDComComment| except that the delimiters are aligned down the 
left side (\<leader\>cl) or both sides (\<leader\>cb). 


**`[count]\<leader\>cu` |NERDComUncommentLine|**  
Uncomments the selected line(s). 

### NERD tree
`F7` NERDTreeTabsToggle

### vim-expand-region
Press `+` to expand the visual selection and `_` to shrink it.
![Vim completion with animation](https://raw.github.com/terryma/vim-expand-region/master/expand-region.gif)

### vim-multiple-cursors
**It's great for quick refactoring**
![Example1](https://github.com/terryma/vim-multiple-cursors/raw/master/assets/example1.gif?raw=true)
* jump to `p` with `fp`
* select the word under cursor with `<C-n>`
* do that two more times for the other two occurrences in the function
* press `c` to change
* type the replacement
* press `<Esc>` to quit back to regular Vim

**Add a cursor to each line of your visual selection**
![Example2](https://github.com/terryma/vim-multiple-cursors/raw/master/assets/example2.gif?raw=true)
* select the line with `V`
* go to the end of the file with `G`
* press `<C-n>` to add a cursor at the beginning of every line and move to normal mode
* press `I` to insert at the beginning of the line
* type `",` move to end of line with `<C-e>`, type another `"` followed by `,`
* move every cursor down one line with `<C-j>`(this is a custom mapping of mine in Insert mode)
* hit `<BS>`, now all the words are on the same line
* the rest is just normal Vim

**Do it backwards too! This is not just a replay of the above gif :)**
![Example3](https://github.com/terryma/vim-multiple-cursors/raw/master/assets/example3.gif?raw=true)
* press `dt"` to delete everything until the first quote
* press `$` to go to end of line
* pree `r`, to replace the `]` with `,`
* go back to the beginning of the line with `^`, press `f`, to find the first comma
* press `v` to select `,` in visual mode, and mash on `<C-n>` until the last occurrence
* press `c` followed by `<CR>` to break the line into multiple lines
* move every cursor up one line with `<C-k>` (again my custom mapping)
* delete the left quote with `C-g<BS>` (custom mapping to move cursor in insert mode)
* go to end of line and delete right quote with `C-e<BS>`

**Add multiple cursors using regexes**
![Example4](https://github.com/terryma/vim-multiple-cursors/raw/master/assets/example4.gif?raw=true)
* press `jV` to visually select the second line
* press `Gk` to select all but the last line
* type `:` followed by the `MultipleCursorsFind` command
* press `o` to toggle the cursor for each visual selection
* press `p` to paste the content of the `+` register (I have `clipboard=unnamedplus` in my vimrc) to each virtual cursor
[see more details](https://github.com/terryma/vim-multiple-cursors/issues/39)

Out of the box, all you need to know is a single key `Ctrl-n`. Pressing the key in Normal mode highlights the current word under the cursor in Visual mode and places a virtual cursor at the end of it. Pressing it again finds the next occurrence and places another virtual cursor at the end of the visual selection. If you select multiple lines in Visual mode, pressing the key puts a virtual cursor at every line and leaves you in Normal mode.

After you've marked all your locations with `Ctrl-n`, you can change the visual selection with normal Vim motion commands in Visual mode. You could go to Normal mode by pressing `v` and wield your motion commands there. Single key command to switch to Insert mode such as `c` or `s` from Visual mode or `i`, `a`, `I`, `A` in Normal mode should work without any issues.

At any time, you can press `<Esc>` to exit back to regular Vim.

Two additional keys are also mapped:
- `Ctrl-p` in Visual mode will remove the current virtual cursor and go back to the previous virtual cursor location. This is useful if you are trigger happy with `Ctrl-n` and accidentally went too far.
- `Ctrl-x` in Visual mode will remove the current virtual cursor and skip to the next virtual cursor location. This is useful if you don't want the current selection to be a candidate to operate on later.

You can also add multiple cursors using a regular expression. The command `MultipleCursorsFind` accepts a range and a pattern, and it will create a virtual cursor at the end of every match within the range. If no range is passed in, then it defaults to the entire buffer.

**NOTE:** If at any time you have lingering cursors on screen, you can press `Ctrl-n` in Normal mode and it will remove all prior cursors before starting a new one.


## Limitations

This image lacks [gdb](https://golang.org/doc/gdb) support. If anyone has managed to get it working on this image, please let me know (breakpoints are not working for me).

the follow link may solve this problem, pls let me know if it work!
[GDB problems inside docker](http://stackoverflow.com/questions/24586086/gdb-problems-inside-docker)
