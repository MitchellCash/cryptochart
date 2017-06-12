# CryptoChart

[CryptoChart.io](https://cryptochart.io), a leaderboard of top open-source cryptocurrencies.

## Contributing

Missing a cryptocurrency here? Just fork the repo and add your currency
as a `<name>.md` in the `source/projects` folder.

Make sure to follow the following rules:

*   **Open Source:** The currency must have a public repository on Github that we can link to and pull in stats from.
*   **Stick to the format:** Fill out all the same fields as the other static site generators in `source/projects`.
*   **Short description:** Keep all the details for the body text, keep the description for the overview page short and sweet.

## Running locally

CryptoChart is built with Middleman. To install and run locally:

    git clone https://github.com/mitchellcash/cryptochart.git
    cd cryptochart
    bundle install (requires ruby 2.1.2 to work w/o errors)
    bundle exec middleman

You'll run into GitHub's API limits very quickly if you just do this. To avoid this we recommend you create a Github API token with permissions to access public repositories and Gist.

Then create a Gist with a single file `data.json` with an empty javascript object literal as content: {}

Then set these environment variables before running middleman:

    export GITHUB_TOKEN=YOUR_TOKEN
    export GIST_ID=ID_OF_YOUR_GIST

Then middleman will use the Gist you specified to archive stats (stars, forks and issues) for the repositories.

## StaticGen

CryptoChart is based off [StaticGen](https://github.com/netlify/staticgen) by [Netlify](https://www.netlify.com).

## License

CryptoChart is released under the [MIT License](LICENSE).
Please make sure you understand its [implications and guarantees](https://writing.kemitchell.com/2016/09/21/MIT-License-Line-by-Line.html).
