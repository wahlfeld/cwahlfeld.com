# creating a new site (assuming you're in ~/projects/personal/hugo)

hugo new site <SITENAME>
cd <SITENAME>
# now you should be in ~/projects/personal/hugo/<SITENAME>
git submodule add https://github.com/<HUGOTHEME>.git themes/<HUGOTHEME>
vim config.toml
   
    baseURL = "http://example.org/"
    languageCode = "en-us"
    title = "dev-wahlfeld.co" # edit this line if you want
    theme = "<HUGOTHEME>" # add this line

# now edit the html files or .conf files depending on the theme to change the website text and elements

# start the website locally to test
hugo server -D

# now to create the website files for public hosting, such as in AWS S3

hugo -v
# or if that doesn't work try this
hugo -v --baseURL "" --buildDrafts --destination public/

# upload the ./public folder to your hosting location and use index.html as the entry point/root file

# Source (kinda): https://gohugo.io/getting-started/quick-start/
