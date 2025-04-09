# Setup Php for development in MAC
1. Install brew https://brew.sh/
2. Install php using brew
   
        brew install php

4. Install composer using brew
   
        brew install composer
6. Install xdebug using brew
   
       brew install xdebug
   In case of any issues
   
   **Problem1**: ERROR: failed to mkdir /opt/homebrew/Cellar/php/8.4.5_1/pecl/20240924
   
   **Solution**:
   
           sudo mkdir -p /opt/homebrew/lib/php/pecl
           sudo chown -R $(whoami) /opt/homebrew/lib/php/pecl
 7. Now install Vscode and extensions

      


