# LPG Cylinder Delivery Queue Dashboard

## Problem

LPG cylinder delivery in India frequently runs delayed, and customers have
little to no visibility into why. A booking is placed, and after that the
process is a black box — there's no way to know:

- Where the order stands in the delivery queue
- Whether it has moved from booked → invoiced → out for delivery
- What the realistic delivery date actually is, versus the date originally promised
- Whether a specific order has silently slipped past its expected date

This lack of transparency erodes trust in the local distributor and leads to
repeated phone calls and follow-ups that could be avoided with a simple
status view.

## Solution

A single-page, self-contained dashboard that gives both customers and the
distributor's staff a live, at-a-glance view of the delivery queue:

- **Queue position** — computed by expected delivery date, so it reflects
  actual dispatch order rather than just booking order
- **Status pipeline** — Booked → Invoiced → Out for Delivery → Delivered
  (or Canceled), shown as a badge plus a compact progress stepper per row
- **Delay flagging** — any order past its estimated delivery date is
  highlighted automatically, surfacing exactly which deliveries need
  attention
- **Agency selection** — multiple agency offices (Ram Agency, Kumar Agency,
  Prabas Agency, plus the Chennai-area agencies: Avadi, Ambatur,
  Washermenpet, Viyarsarpadi) can be filtered from one dropdown, each with
  its own queue, city/state, and accent color
- **Search & filter** — find any booking by name, booking ID, or area,
  and filter by status
- **Mobile-friendly** — on small screens the table condenses to just
  Booking ID, Gas Connection ID, Queue Position, and Status, and the
  summary metric cards stack full-width instead of a 4-column grid

## Brief

- **Format:** Single static HTML file (`index.html`) — HTML, CSS, and
  vanilla JS, no build step or backend required
- **Data:** Currently uses generated mock bookings for demonstration;
  intended to be wired up to a real orders API (e.g. a Django backend)
  for production use
- **Deployment:** Static-hosting ready — deployable as-is to Vercel,
  Netlify, or any static file host
- **Audience:** LPG customers wanting transparency into their delivery
  status, and distributor staff needing a quick operational view of the
  queue
