# Amor De Goa — Airbnb Listing Clone (React + Vite)

A React recreation of the Airbnb listing page reference, including the Photo Tour and Lightbox overlays.

## Run it

npm install
npm run dev        # http://localhost:5173

npm run build       # production build to /dist
npm run preview

## Structure

src/
  data/listing.js         shared content (photos, reviews, nearby stays, co-hosts)
  components/
    Header.jsx             top nav bar
    Gallery.jsx             hero photo grid + "Show all photos"
    SubNav.jsx              sticky Photos/Amenities/Reviews/Location tabs + price/Reserve
    ListingBody.jsx         all left-column content (favourite card, host, amenities,
                             calendar, reviews, map, host section, things to know, nearby stays)
    BookingCard.jsx         sticky right-hand booking card
    PhotoTour.jsx           full-screen photo grid overlay
    Lightbox.jsx            single-photo viewer with prev/next + keyboard (←/→/Esc)
  App.jsx                   composes everything, owns tour/lightbox state
  App.css                   all styles

## Notes

- Photos are hotlinked from Lorem Picsum (https://picsum.photos) as stand-ins — swap the
  URLs in src/data/listing.js for real listing photos.
- Keyboard: Escape closes the tour/lightbox, ArrowLeft/ArrowRight navigate the lightbox
  (disabled at the first/last photo, no wrap-around), and focus returns to the button
  that opened the overlay when it closes.
- Desktop layout only, per the assignment scope; a basic responsive breakpoint at 960px
  is included but not the primary target.
