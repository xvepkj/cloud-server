source ~/cloudserver/venv/bin/activate
python app.py


cloudflared tunnel --url http://localhost:5000 &> cloudflared.log &
tail -f cloudflared.log

grep -o 'https://[^ ]*trycloudflare.com' cloudflared.log
