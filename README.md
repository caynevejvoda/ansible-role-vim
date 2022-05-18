Ansible Role: Vim
=========

[![CI](https://github.com/caynevejvoda/ansible-role-vim/workflows/CI/badge.svg?event=push)](https://github.com/caynevejvoda/ansible-role-vim/actions?query=workflow%3ACI)

Install and configure vim with plugins for multiple users.

Requirements
------------

N/A

Role Variables defaults
-----------------------
Available variables are listed below, along with default values (see `defaults/main.yml`):
List of users for whom vim is to be installed.

    vim_user: 
      - root

Plugin names.

    vim_plugins: []

Plugin git url.

    vim_plugin_urls: []

Content of .vimrc.

    vim_vimrc_content: |

Role Variables example
----------------------
    vim_user:
      - root
      - ansible

    vim_plugins:
      - vim-airline
      - nerdtree
      - nord-vim
      - vim-airline-themes
      - vim-yaml

    vim_plugin_urls:
      - https://github.com/vim-airline/vim-airline.git
      - https://github.com/preservim/nerdtree.git
      - https://github.com/arcticicestudio/nord-vim.git
      - https://github.com/vim-airline/vim-airline-themes.git
      - https://github.com/stephpy/vim-yaml.git

    vim_vimrc_content: |
      set number
      set mouse=a

      let g:floaterm_keymap_toggle = '<F12>'
      let g:floaterm_width = 0.9
      let g:floaterm_height = 0.9

      let g:airline_theme='<theme>'
      syntax on
      set t_Co=256
      set cursorline
      silent! colorscheme nord
      let g:airline_theme='nord'
      let g:airline_powerline_fonts=1

      if exists('+termguicolors')
        let &t_8f = "\<Esc>[38;2;%lu;%lu;%lum"
        let &t_8b = "\<Esc>[48;2;%lu;%lu;%lum"
        set termguicolors
      endif

      nnoremap <leader>n :NERDTreeFocus<CR>
      nnoremap <C-n> :NERDTreeToggle<CR>
      nnoremap <C-f> :NERDTreeFind<CR>

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      vars_files:
        - vars/main.yml
      roles:
        - role: caynevejvoda.vim

License
-------

MIT

Author Information
------------------

This role was created in 2022 by Cayne Vejvoda.
