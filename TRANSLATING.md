### Translating the toolkit into your language

As part of our mission to democratize machine learning, we'd love to make the educational toolkit available in many more languages! Follow the steps below if you want to help translate the toolkit into your language 🙏.

**🍴 Fork the repository**

To get started, you'll first need to [fork this repo](https://docs.github.com/en/get-started/quickstart/fork-a-repo). You can do this by clicking on the **Fork** button on the top-right corner of this repo's page.

Once you've forked the repo, you'll want to get the files on your local machine for editing. You can do that by cloning the fork with Git as follows:

```bash
git clone https://github.com/YOUR-USERNAME/education-toolkit
```

**📋 Copy-paste the English version with a new language code**

The toolkit files are organised into one main directory:

- [`tutorials`](https://github.com/huggingface/education-toolkit/tree/main/tutorials): all the toolkit materials organized by language.

You'll only need to copy the files in the [`tutorials/EN`](https://github.com/huggingface/education-toolkit/tree/main/tutorials/EN) directory, so first navigate to your fork of the repo and run the following:

```bash
cd ~/path/to/education-toolkit
cp -r tutorials/EN tutorials/LANG-ID
```

Here, `LANG-ID` should be one of the ISO 639-1 or ISO 639-2 language codes -- see [here](https://www.loc.gov/standards/iso639-2/php/code_list.php) for a handy table.

**✍️ Start translating**

Now comes the fun part - translating the text in the `md` and `ipynb` files!

> 🙋 If you'd like others to help you with the translation, you can either [open an issue](https://github.com/huggingface/education-toolkit/issues) or tag @[LepercqViolette](https://twitter.com/LepercqViolette)
 on Twitter to gain some visibility.