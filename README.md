# all-in-one-color.nvim

**WIP: Please don't use this tool for now, it's still not done yet.**

I'm greedy that I want the **most popular** Neovim colorschemes than just one, I'm playful that I want to change colorscheme from time to time. Are you like me?

This is it!

* Auto-generate collect the most colorschemes from below websites:



* Install them as git submodules of this plugin.
* Multiple switches on these colors:
  * Policy: suffle playback, play in order, single cycle.
  * Timing: on startup, 

> Note: **most popular** colorschemes are picked from below websites:
> - [vimcolorscheme.com/top](https://vimcolorschemes.com/top)
> - [awesome-neovim#colorscheme](https://www.trackawesomelist.com/rockerBOO/awesome-neovim/readme/#colorscheme)
>
> With below conditions:
>
> 1. Github stars &ge; 500.
> 2. Last git commit in 3 years.
> 3. For multiple variants of a colorscheme, keep the one with more plugins
   support, stars or git commits.

## Requirement

Neovim &ge; 0.8.

## Usage

### Collect colorschemes

The collector is implemented by selenium based crawler, depends on
python3 and [chromedriver](https://chromedriver.chromium.org/downloads).

1. Install pip libraries:

   ```bash
   pip3 install selenium
   pip3 install tinydb
   ```

2. Run python scripst:

   ```bash
   python3 ./fetch.py
   python3 ./clone.py
   python3 ./build.py
   ```

### Import to nvim config

For lazy.nvim:

```lua
{
    'linrongbin16/colorswitch.nvim',
    lazy = true,
    priority = 1000,
    dependencies = { 'linrongbin16/logger.nvim' },
    config = function()
        require('colorswitch').setup()
    end
}
```

For packer.nvim:

For vim-plug:
