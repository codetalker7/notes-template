# notes-template
These are some tools which I use for live note taking. I use [pandoc](https://pandoc.org/) to convert the markdown files to PDFs using `pdflatex`. The benefit of pandoc is that it also allows LaTeX macros, something which is extremely useful.

To watch the file I'm currently editing, I use the very straightforward [docwatch](https://github.com/elcorto/docwatch). It has support for pandoc and is very easy to use. For example, to start watching the `template.md` file, just do 
```bash
docwatch -o "header.yaml" template.md
```
This will open `template.md` in Vim and will also initiate pandoc's work. `docwatch`'s `-o` options is used to specify any additional options to pass to `pandoc`; in this case, we pass the `header.yaml` configuration file.

I also use the [vim-pandoc](https://github.com/vim-pandoc/vim-pandoc) and the [vim-pandoc-syntax](https://github.com/vim-pandoc/vim-pandoc-syntax) plugins, which are a must use for integration of pandoc with Vim.

For the [YouCompleteMe](https://github.com/ycm-core/YouCompleteMe) plugin to work on markdown files, the easiest thing to do is to set the blacklist to empty in the `~/.vimrc` file. 

```bash
let g:ycm_filetype_blacklist = {}
```

Finally, we come to snippets. For this, the best tool to use is [UltiSnips](https://github.com/SirVer/ultisnips). For convenience, I have defined a `markdown.snippets` file, which contains a few snippets that I often use while making the notes. To let UltiSnips know which directory to look for snippets, add the following line to your `~/.vimrc`.

```bash
let g:UltiSnipsSnippetDirectories=["UltiSnips", "mysnippets"]
```

Then UltiSnips will look for snippets in `~/.vim/mysnippets`. A nice UltiSnips tutorial is available at https://developpaper.com/vim-code-snippet-plug-in-ultisnips-usage-tutorial/.
