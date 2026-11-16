# The Fitting Room

A student concept prototype of an AI virtual fitting room and stylist, built for a university digital strategy project about Next. It is not an official Next website.

Live page: https://joelahutchison-code.github.io/DigitalFittingroom/

## What it does

**Fitting room (strategy 1)**
- Shows nine pieces, using free stock photographs of real clothes: tops, a suit jacket, trousers and a tie.
- Takes a photo of you and your usual size, after you tick a consent box.
- A try-on model generates a new image of you wearing the piece.
- Pick another size and an image-editing model redraws the image looser or tighter. Fit notes, a recommended size and a return-risk figure change with it.
- A video model turns a look into a short runway clip.
- Share or save a look. Saved and shared images carry an AI-generated label.

**Stylist (strategy 2)**
- Reads your style from up to six photos of outfits you like to wear. A small image-and-text model runs inside the browser, scores each photo against four styles (tailored, smart casual, relaxed casual, streetwear) and the page suggests the pieces that match. The photos are not uploaded and are not kept. You can also choose the style yourself.
- Plans an outfit for your style and occasion within your budget, checks stock in your size, holds a delivery slot and stops for your approval.
- Tries the whole outfit on you, and books a return afterwards.

## What is real and what is simulated

- Real: the four AI models and everything they produce. Three generate images and video on Hugging Face servers. The fourth reads style photos on your own device.
- Simulated: stock, prices, delivery, fit data and return-risk figures. The stylist follows written rules where a real agent would reason with a language model over live systems. Each piece is tagged by hand with the styles it suits, where a retailer would learn this from sales and returns. Size images are AI illustrations, not measurements.

## Running it

It is one static file, `index.html`, served by GitHub Pages.

Without a Hugging Face token the shared anonymous allowance covers about three images a day. For your own daily allowance, create a free account, make a read token at https://huggingface.co/settings/tokens and paste it under AI settings on the page. The token is stored only in your browser. Never commit it to this repository.

The first style reading downloads the style model once, about 55 MB. It needs no token and no allowance.

## Credits

- Product photographs from Pexels, free to use under the Pexels licence: mockupbee, dayong tien, Jonathan Borba, Artem Podrez, Polina Chistyakova, James Frid, Alexander Mass, Engin Akyurt, Dom J. Links are on the page.
- Try-on: FASHN VTON 1.5 (`fashn-ai/fashn-vton-1.5`), with Leffa and IDM-VTON as fallbacks.
- Size redraw and outfit layering: FLUX.2 klein (`black-forest-labs/FLUX.2-klein-9B`, fallback `FLUX.2-klein-4B`).
- Runway clip: Wan 2.2 (`zerogpu-aoti/wan2-2-fp8da-aoti-faster`).
- Style reading: MobileCLIP S0 by Apple (`Xenova/mobileclip_s0`), run in the browser with Transformers.js 3.7.6. Apple licenses the model for research use only, so a commercial service would need a different model.
- The image and video models run as public Hugging Face Spaces. Built with Claude.
