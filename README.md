# URLShortener

<p align="center">
    <a href="https://github.com/1StranGe/URLShortener"><img src="https://i.ibb.co/8zPJpX8/Logo-removebg-preview.png" alt="URLShortener Logo" border="0"></a>
    <br>A Free And Simple URL Shortener
</p>

---

[![GitHub pull-requests](https://img.shields.io/github/issues-pr/SVijayB/URLShortener.svg)](https://github.com/SVijayB/URLShortener/pulls)
[![GitHub issues](https://img.shields.io/github/issues/SVijayB/URLShortener.svg)](https://github.com/SVijayB/URLShortener/issues)
[![GitHub contributors](https://img.shields.io/github/contributors/SVijayB/URLShortener.svg)](https://github.com/SVijayB/URLShortener/graphs/contributors)

[![GitHub license](https://img.shields.io/github/license/SVijayB/URLShortener.svg)](https://github.com/SVijayB/URLShortener/blob/master/LICENSE)
[![GitHub release](https://img.shields.io/github/release/SVijayB/URLShortener.svg)](https://github.com/SVijayB/URLShortener/releases)
[![GitHub repo size](https://img.shields.io/github/repo-size/SVijayB/URLShortener)](https://github.com/SVijayB/URLShortener)

[![Code of Conduct](https://img.shields.io/badge/code%20of-conduct-ff69b4.svg?style=flat)](https://github.com/SVijayB/.github/blob/master/URLShortener/CODE_OF_CONDUCT.md)
[![Open Source Love svg1](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/SVijayB/.github/blob/master/URLShortener/CONTRIBUTING.md)

## Table of Contents

- [Motivation](#Motivation)
- [Installation](#Installation)
- [Usage](#Usage)
- [Contributing](#Contributing)
- [License](#License)

## Motivation

When sites like <a href="https://bitly.com/">Bit.ly</a> and <a href="https://hootsuite.com/pages/owly">Ow.ly</a> are present, why would you want to build a custom short URL? Especially when they offer analytics?

For one, they are insanely expensive. Bit.ly for example offers a basic plan at $29/month. Which is a lot.

This is a completely free to use and simple tool that lets you create Short Url Links for your custom **Domains**.

## Installation

This module is distributed via <a href="https://www.npmjs.com/">npm</a> packet manager, which is contained within <a href="https://nodejs.org/en/">node</a> and should be installed as one of your project's `devDependencies`:

<pre>
npm install --save-dev netlify-shortener
</pre>

## Usage

1. Create a GitHub Repository and initialize it with a `_redirects` file.

  This _redirects file should contain links to all the websites for which you want to create a short URL in the below format : 

<pre>
/go         http://google.com          #Custom URL
/gh         http://github.com          #Custom URL

/*          https://your-website.com   #Default Link
</pre>

You can now modify the contents of your **"_redirects"** file to create your own custom link.

2. Create an account on <a href="https://www.netlify.com/">netlify</a>. Log in and select "New site from Git". Select GitHub and give it permissions to access your GitHub repository. Now, choose the GitHub repository that you created earlier and click on deploy. 

3. Click on your site and navigate to domain settings. Here, choose your custom domain. You can either buy a new one or create a short netlify domain for free.

Netlify will automatically deploy the result when you push to this repository.

Once you are done with this. You can manually create your own short URL by editing the contents of `_redirects` file.

Following the above example, 
<pre>
yourdomain.com/gh       #should open github.com
yourdomain.com/go       #should open google.com
</pre>

However, you can also automate this with a few simple steps.

1. Go to your working directory(Your repository), and in your terminal type : `npm init -y`

This should create a package.json file.

2. In your terminal enter :

    `npm install --save-dev netlify-shortener`

And this should add netlify-shortener to your node_modules.

3. You will have to edit your package.json file to include netlify-shortener in scripts and modify your baseURL

<pre>
{
  "baseUrl": "https://svj.netlify.app",     #Modify to use your custom address.
  "scripts": {
    "shorten": "netlify-shortener"          #Add netlify-shortener to scripts.
  }
}
</pre>

You are all set and ready to go.

Open your terminal and run this :

<pre>
npm run shorten                         # simply formats your _redirects file
npm run shorten https://yahoo.com yh    # adds yh as a short URL for you. 
</pre>

If you have finished the above steps, `yourdomain.com/yh` should lead you to Youtube.

The `netlify-shortener` does a few things:

1. adds the URL to the top of `_redirects`
2. runs a git commit and push (this will trigger netlify to deploy your new redirect)
3. Copies the short URL to your clipboard

## Contributing 

To contribute to URLShortener, fork the repository, create a new branch and send us a pull request. Make sure you read [CONTRIBUTING.md](https://github.com/SVijayB/.github/blob/master/URLShortener/CONTRIBUTING.md) before sending us Pull requests. 

Also, thanks for contributing to Open-source!

## License 

URLShortener is under The MIT License. Read the [LICENSE](https://github.com/1StranGe/URLShortener/blob/master/LICENSE) file for more information.



