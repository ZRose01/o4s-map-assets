# Event images

Never drop raw photos here — run them through the optimizer, which
resizes/compresses into this directory (~40 KB each):

    python3 ../../optimize_images.py path/to/photo.jpg

Then put the output filename in the `Image` column of the tracker CSV
and re-run `build_events.py`. Events without an image get a neutral
placeholder automatically.

The 40 KB budget matters: worst-case traffic is 3,500 visits/day × 91
images, ~10M image requests/month. Images are therefore served through
jsDelivr (`cdn.jsdelivr.net/gh/ZRose01/o4s-map-assets@main/images/`),
which has no bandwidth cap — but it caches files for ~12 hours, so
**never replace an image under the same filename**; add the fixed
version under a new name and update the CSV.
