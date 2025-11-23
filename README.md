📡 SXM Tracker

A self-hosted tool to track, record, and sync SiriusXM radio history to
your local media server.

SXM Tracker monitors your favorite satellite radio channels in
real-time. When a song plays, it checks if you own it. If not, it
automatically finds a high-quality version, downloads it via Slskd, and
syncs it to your Navidrome playlists—all without creating duplicates.

------------------------------------------------------------------------

✨ Features

🔄 Smart Playlist Sync
Automatically creates and updates playlists in Navidrome matching the
radio station’s history.

⬇️ Automated Downloads
Integrates with Slskd to automatically find and download missing tracks
in FLAC or 320kbps MP3.

🛡️ Duplicate Protection
Intelligent database remembers every song ever downloaded to prevent
duplicate files, even if the song plays on another channel.

💻 Live Console
Built-in “Hacker Terminal” showing real-time logs, download activity,
and system events.

📱 Mobile-Friendly UI
Responsive interface to browse history, view stats, and manage stations.

🚀 Dockerized
One-click deployment via Docker Compose.

------------------------------------------------------------------------

📸 Screenshots

• Dashboard
• Live Console
• Channel History
• Real-time Logs

------------------------------------------------------------------------

🛠️ Prerequisites

You need:

• Docker Desktop or Docker Engine + Compose
• (Optional) Navidrome for playlist syncing
• (Optional) Slskd for music downloads

------------------------------------------------------------------------

🚀 Quick Start

1. Download & Extract

Clone or download the repo (e.g., SXM-Tracker).

2. Create .env

— SXM TRACKER CONFIG —

Navidrome (For Playlist Sync)

ND_URL=http://host.docker.internal:4533 ND_USER=admin
ND_PASS=your_navidrome_password

Slskd (For Music Downloads)

SLSKD_URL=http://host.docker.internal:5030
SLSKD_API_KEY=your_slskd_api_key

System Settings

FETCH_INTERVAL=60 MAX_WORKERS=3

3. Run

docker-compose up -d

4. Open Dashboard

http://localhost:8080

------------------------------------------------------------------------

⚙️ Configuration

Inside the Web UI:

1.  Click Settings
2.  Search for a channel (e.g., “BPM”, “Hits 1”)
3.  Check the box to track it
4.  Click Save

------------------------------------------------------------------------

📂 Project Structure

SXM-Tracker/ ├── data/ # Database, logos, history ├── downloads/ # Slskd
download folder ├── docker-compose.yml ├── Dockerfile ├── nginx.conf ├──
song_tracker.py ├── index.html └── .env

------------------------------------------------------------------------

❓ FAQ

Songs download but don’t show in playlists? Navidrome must scan them
first. Set ND_SCANINTERVAL=1m or 5m.

How to view live script activity? Open the floating Terminal icon. Green
= success, Blue = downloading, Red = error.

Force sync old history? Settings → Maintenance → Force Sync All

------------------------------------------------------------------------

📝 License

MIT License
