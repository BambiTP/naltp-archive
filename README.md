# NALTP Archive

Home page for the NALTP (North American TagPro leagues) archive: https://bambitp.github.io/naltp-archive/

The archive itself is served from a home machine through a Cloudflare quick tunnel, which is
handed a new address every time it restarts. There are two ways to reach it, and which one you
want depends on whether you are writing the address down anywhere.

**A link that keeps working.** A redirect that always points at wherever the tunnel is now:

    https://tagpro-archive-tunnel.bambitagpro.workers.dev/h/naltp/go/<path>

The path carries through, so `/h/naltp/go/export/teams.csv` fetches that file. This is the
address to put in a script or hand to someone else, because it survives a rotation. While the
home machine is down it answers 503 with a short explanation instead of a dead link.

**The current address itself.** `tunnel.json` holds it in its `url` field, updated automatically
whenever it changes. The pages here read that file directly; anything else reading it has to read
it again after every rotation, which is what the redirect above exists to avoid.
`<base>/tunnel-check.txt` contains `naltp-archive` when the server is up.

Whether the host is online, and how long ago it last checked in:

    https://tagpro-archive-tunnel.bambitagpro.workers.dev/h/naltp/status

See `llms.txt` for every path and data format.
