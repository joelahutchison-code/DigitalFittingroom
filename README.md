# The Fitting Room

A student concept prototype of an AI virtual fitting room, built for a university digital strategy project about Next. It is not an official Next website.

## What it does

- Shows five pieces, using free stock photographs of real clothes.
- Takes a photo of you and your usual size.
- Sends your photo and the product photo to a free virtual try-on model on Hugging Face, which generates a new image of you wearing the piece.
- Keeps the images you have made in your browser, so they reopen at once.
- Gives fit notes for each size. The image itself does not change with size.

## Running it

It is one static file, `index.html`. Open it in a browser, or serve the folder with GitHub Pages.

For your own daily allowance on Hugging Face, create a free account, make a read token at https://huggingface.co/settings/tokens and paste it under AI settings on the page. The token is stored only in your browser. Never commit it to this repository.

## Credits

- Product photographs from Pexels, free to use under the Pexels licence: mockupbee, dayong tien, Artem Podrez, Polina Chistyakova, James Frid. Links are on the page.
- Try-on models: FASHN VTON 1.5 (`fashn-ai/fashn-vton-1.5`), with Leffa (`franciszzj/Leffa`) and IDM-VTON (`yisol/IDM-VTON`) as fallbacks, all run as public Hugging Face Spaces.
- Built with Claude.
