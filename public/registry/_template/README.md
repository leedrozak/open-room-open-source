# Building Your Room

## Setup

1. Copy this folder to `public/registry/your-room-id/` — use the room ID you got when you reserved your spot.
2. Add your background image as `background.jpeg` (WebP preferred, max 200KB).
3. Edit `config.json` to match your room.

## config.json fields

| Field | Description |
|---|---|
| `room_display_name` | The name shown inside your room |
| `owner` | Your GitHub username |
| `background_image` | Path to your image — replace `your-room-id` with your actual ID |
| `hotspots` | Array of clickable zones |

## Hotspot fields

| Field | Description |
|---|---|
| `id` | A unique string, no spaces |
| `label` | Tooltip text shown on hover |
| `x` | Left edge of the hotspot, as a % of image width (0–100) |
| `y` | Top edge of the hotspot, as a % of image height (0–100) |
| `width` | Width of the hotspot as a % of image width |
| `height` | Height of the hotspot as a % of image height |
| `action` | What happens on click — see below |

## Actions

**`navigate_floor`** — sends the visitor back to the floor plan. Use this on your door.

```json
{
  "action": "navigate_floor"
}
```

**`open_url`** — opens a link in a new tab. Use this for external links.

```json
{
  "action": "open_url",
  "url": "https://yoursite.com"
}
```

## Tips

- Use your AI to help position hotspots. Ask it to look at your background image and estimate x/y/width/height percentages for each clickable element.
- Preview your room locally by running `npm run dev` and visiting `/preview/your-room-id`.
- Every room needs at least one `navigate_floor` hotspot so visitors can leave.

## Building codes

- Background image: JPEG or WebP, **max 200KB**
- Total room folder: **max 5MB**
- One room per builder

## Submitting

Open a Pull Request from your fork to the main repo. Include a screenshot of your room in the PR description.
