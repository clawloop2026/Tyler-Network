# Unsupported Shadowrocket Rules

These rules were present in the source `.conf` but are not included in the shared Mihomo/Clash YAML because they are not consistently supported across FlClash, Stash, and Mihomo.

```text
USER-AGENT,AppStore*,DIRECT
USER-AGENT,com.apple.appstored*,DIRECT
USER-AGENT,TestFlight*,DIRECT
USER-AGENT,*bili*,DIRECT
USER-AGENT,QIYI*,DIRECT
USER-AGENT,iQiYi*,DIRECT
USER-AGENT,MOO*,DIRECT
USER-AGENT,TencentMidasConnect*,DIRECT
USER-AGENT,%E7%BD%91%E6%98%93%E4%BA%91%E9%9F%B3%E4%B9%90*,DIRECT
USER-AGENT,NeteaseMusic*,DIRECT
USER-AGENT,AbemaTV*,Proxy
USER-AGENT,InstantVideo.US*,Proxy
USER-AGENT,Prime%20Video*,Proxy
USER-AGENT,Anime*,Proxy
USER-AGENT,BBCiPlayer*,Proxy
USER-AGENT,TwDramas*,Proxy
USER-AGENT,PCCW*,Proxy
USER-AGENT,FOX%20NOW*,Proxy
USER-AGENT,FOXPlus*,Proxy
USER-AGENT,HBO%20NOW*,Proxy
USER-AGENT,Hulu*,Proxy
USER-AGENT,WeMusic*,Proxy
USER-AGENT,JOOX*,Proxy
USER-AGENT,mytv*,Proxy
USER-AGENT,skygo*,Proxy
USER-AGENT,SoundCloud*,Proxy
USER-AGENT,*Spotify*,Proxy
USER-AGENT,*youtube*,Proxy
USER-AGENT,YouTube*,Proxy
USER-AGENT,%E7%BA%BD%E7%BA%A6%E6%97%B6%E6%8A%A5*,Proxy
USER-AGENT,AwemeI18n*,Proxy
USER-AGENT,Coinbase*,Proxy
USER-AGENT,Instagram*,Proxy
USER-AGENT,Resilio Sync*,Proxy
USER-AGENT,WhatsApp*,Proxy
USER-AGENT,OneDrive*,Proxy
USER-AGENT,hide*,DIRECT
USER-AGENT,MicroMessenger*,DIRECT
USER-AGENT,PayPal*,DIRECT
USER-AGENT,TeamViewer*,DIRECT
USER-AGENT,TIM*,DIRECT
USER-AGENT,ting_en,DIRECT
USER-AGENT,WebTorrent*,DIRECT
USER-AGENT,WeChat*,DIRECT
URL-REGEX,(Subject|HELO|SMTP),DIRECT
URL-REGEX,(api|ps|sv|offnavi|newvector|ulog\.imap|newloc)(\.map|)\.(baidu|n\.shifen)\.com,DIRECT
URL-REGEX,(.+\.|^)(360|so|qihoo|360safe|qhimg|360totalsecurity|yunpan)\.(cn|com),DIRECT
URL-REGEX,(.+\.)?(torrent|announce\.php\?passkey=|tracker|BitTorrent|bt_key|ed2k|find_node|get_peers|info_hash|magnet:|peer_id=|sandai|Thunder|XLLiveUD|xunlei)(\..+)?,DIRECT
```
