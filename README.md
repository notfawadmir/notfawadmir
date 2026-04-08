
<h2 class="sr-only">Operator: Red Cell — A hacking RPG using real cybersecurity tools: Nmap, Burp Suite, sqlmap, Metasploit, LinPEAS, Scanibal, WebHawk</h2>
<style>
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
@keyframes fadeUp{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:none}}
@keyframes flicker{0%,100%{opacity:1}91%{opacity:.95}92%{opacity:1}95%{opacity:.97}}
@keyframes pulse{0%,100%{opacity:.6}50%{opacity:1}}
@keyframes scanline{0%{top:-10%}100%{top:110%}}
#g{background:#050a05;color:#00ff41;font-family:'Courier New','Lucida Console',monospace;min-height:680px;border-radius:8px;overflow:hidden;position:relative;border:1px solid rgba(0,255,65,.2);animation:flicker 12s infinite}
#g::after{content:'';position:absolute;inset:0;background:repeating-linear-gradient(0deg,rgba(0,0,0,.04)0px,rgba(0,0,0,.04)1px,transparent 1px,transparent 3px);pointer-events:none;z-index:99}
.scanline{position:absolute;left:0;right:0;height:3%;background:linear-gradient(rgba(0,255,65,.03),transparent);animation:scanline 6s linear infinite;pointer-events:none;z-index:98}
#mc{position:absolute;top:0;left:0;width:100%;height:100%;opacity:.12;pointer-events:none;z-index:0}
#sc{position:relative;z-index:10}
.scr{padding:28px 32px;min-height:680px;display:flex;flex-direction:column;animation:fadeUp .35s ease}
.big-title{font-size:44px;letter-spacing:10px;color:#00ff41;margin:0;line-height:1}
.dim{color:rgba(0,136,34,.7);font-size:11px;letter-spacing:3px}
.sep{border:none;border-top:1px solid rgba(0,255,65,.15);margin:16px 0}
.hud{display:flex;justify-content:space-between;align-items:center;border:1px solid rgba(0,255,65,.2);padding:10px 16px;margin-bottom:20px;border-radius:4px;background:rgba(0,255,65,.02);font-size:11px;letter-spacing:2px;flex-wrap:wrap;gap:8px}
.hl{color:rgba(0,136,34,.8);font-size:10px;margin-bottom:3px}
.hv{color:#00ff41;font-weight:bold;font-size:13px}
.abar{height:5px;background:rgba(0,0,0,.5);border-radius:3px;overflow:hidden;width:100px;margin-top:4px}
.afill{height:100%;border-radius:3px;transition:width .6s ease,background .4s}
.narr{border-left:2px solid rgba(0,255,65,.3);padding-left:16px;margin:12px 0;color:rgba(136,200,136,.9);font-size:13px;line-height:1.85;flex:1;min-height:100px;white-space:pre-wrap}
.choices{display:flex;flex-direction:column;gap:8px;margin-top:20px}
.cbtn{background:rgba(0,255,65,.02);border:1px solid rgba(0,255,65,.25);color:#00ff41;font-family:'Courier New',monospace;font-size:12px;padding:12px 14px;text-align:left;cursor:pointer;border-radius:4px;transition:all .2s;letter-spacing:.5px;width:100%}
.cbtn:hover:not(:disabled){background:rgba(0,255,65,.08);border-color:#00ff41;transform:translateX(5px)}
.cbtn:disabled{opacity:.35;cursor:not-allowed;transform:none}
.cbtn-desc{font-size:11px;color:rgba(0,136,34,.8);margin-top:5px}
.pbtn{background:rgba(0,255,65,.06);border:1px solid #00ff41;color:#00ff41;font-family:'Courier New',monospace;font-size:13px;padding:12px 28px;cursor:pointer;letter-spacing:3px;text-transform:uppercase;border-radius:4px;transition:all .2s;display:none}
.pbtn:hover{background:rgba(0,255,65,.15)}
.pbtn.vis{display:inline-block}
.tag{display:inline-block;border:1px solid;font-size:10px;padding:2px 7px;border-radius:2px;letter-spacing:1px;margin-left:8px;vertical-align:middle;white-space:nowrap}
.tg{color:#00cc33;border-color:rgba(0,204,51,.4);background:rgba(0,204,51,.08)}
.tr{color:#ff5555;border-color:rgba(255,49,49,.4);background:rgba(255,49,49,.08)}
.ta{color:#ffb700;border-color:rgba(255,183,0,.4);background:rgba(255,183,0,.08)}
.rcard{border:1px solid rgba(0,255,65,.2);padding:14px;border-radius:4px;flex:1;background:rgba(0,255,65,.03)}
.rcard-r{border-color:rgba(255,49,49,.25);background:rgba(255,49,49,.04)}
.sbox{border:1px solid rgba(0,255,65,.15);padding:12px;border-radius:4px;background:rgba(0,255,65,.02)}
.sbox .n{font-size:28px;color:#00ff41;margin-top:4px}
.sbox .l{font-size:10px;color:rgba(0,136,34,.8);letter-spacing:2px}
.g2{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.cursor-blink::after{content:'█';animation:blink 1s step-end infinite;color:#00ff41}
.log-ok{color:#00ff41}.log-warn{color:#ffb700}.log-err{color:#ff5555}.log-dim{color:rgba(0,136,34,.8)}
.pbar{height:3px;background:rgba(0,0,0,.4);border-radius:2px;overflow:hidden;margin:10px 0}
.pfill{height:100%;background:#00ff41;border-radius:2px;width:0;transition:width 2s linear}
</style>

<div id="g">
  <div class="scanline"></div>
  <canvas id="mc"></canvas>
  <div id="sc"></div>
</div>

<script>
const $=id=>document.getElementById(id);
const sc=$('sc');

const G={alert:0,score:0,mission:0,choices:[],alive:true};

const MS=[
  {id:'01',name:'FIRST CONTACT',target:'192.168.1.0/24 — CorpHQ Internal Network',
   tools:['Nmap','Shodan','Whois','Scanibal'],
   brief:`CLIENT: SecureBank Ltd. SCOPE: Full internal pentest.\nOBJECTIVE: Map the attack surface. Find entry vectors.\n\nYou're in. VPN tunnel established. Target network is live.\nIntrusion detection is active — traffic anomalies are flagged.\nYour first move defines the op.\n\nRecon approach?`,
   opts:[
    {lbl:'> nmap -A -T4 192.168.1.0/24',desc:'Aggressive full scan — fast but extremely noisy',tag:'AGGRESSIVE',tc:'tr',ad:38,pts:95,
     res:`[nmap] Sending 10,000+ packets across subnet...\n[+] Scan complete in 3m 42s. 23 hosts up.\n[+] Apache 2.4.29 on .11, MySQL 5.7 on .14, SSH on .22\n[+] corp-portal.company.com → 192.168.1.11\n[!] ALERT: IDS flagged 847 anomalous packets.\n[!] Security analyst on-call has been notified.\n[~] Intel acquired — but your fingerprints are everywhere.`,rt:'warn'},
    {lbl:'> nmap -sS -T2 --reason 192.168.1.0/24',desc:'SYN stealth scan — quieter, surgical',tag:'OPTIMAL',tc:'tg',ad:9,pts:150,
     res:`[nmap] Half-open SYN scan initiated (T2 timing)...\n[+] 17 minutes elapsed. Zero IDS triggers.\n[+] 23 hosts identified. All ports mapped cleanly.\n[+] Apache 2.4.29 (.11), MySQL 5.7 (.14), Tomcat 9 (.19)\n[+] corp-portal.company.com resolving to 192.168.1.11\n[+] Version fingerprints acquired. CVE candidates noted.\nClean recon. No signature. Textbook operator.`,rt:'good'},
    {lbl:'> shodan search "CorpHQ" + whois + LinkedIn OSINT',desc:'Passive only — zero packets sent to target',tag:'PASSIVE',tc:'ta',ad:0,pts:65,
     res:`[Shodan] 3 externally exposed IPs matched.\n[+] Email naming schema: firstname.lastname@corp.com\n[+] CMS version leaked via Shodan banner.\n[+] 2 employees listing sysadmin role on LinkedIn.\n[!] Missing: internal topology. Major blind spots remain.\n[~] Zero risk, but incomplete picture. You'll need more.`,rt:'warn'},
   ]},
  {id:'02',name:'WEB VECTOR',target:'corp-portal.company.com — Login Portal (PHP/MySQL)',
   tools:['Burp Suite','sqlmap','WebHawk','OWASP ZAP'],
   brief:`TARGET: corp-portal.company.com\nSTACK: Apache 2.4.29 / PHP 7.2 / MySQL backend\n\nManual review: login form returns "Admin" in a response\nheader when user_id=1 is submitted. Classic tell.\n\nThis parameter is almost certainly injectable.\nYou have a WAF to bypass and limited time.\n\nHow do you exploit it?`,
   opts:[
    {lbl:'> sqlmap -u "corp-portal/login.php" --dbs --level=5',desc:'Full automated dump — thorough, but loud',tag:'NOISY',tc:'tr',ad:48,pts:105,
     res:`[sqlmap] Running 847 payloads against user_id param...\n[+] SQL injection confirmed: error-based, UNION-based\n[+] Backend: MySQL 5.7.29-log\n[+] Databases: corp_main, users, audit_logs, sessions\n[!] WAF triggered: 23 blocked requests logged to SIEM\n[!] Security team paged. Investigation timer: 15 min.\n[~] Data extracted. But your noise level is unacceptable.`,rt:'warn'},
    {lbl:'> burpsuite → manual UNION injection via Intruder',desc:'Surgical hand-crafted payloads — precise, stealthy',tag:'OPTIMAL',tc:'tg',ad:11,pts:185,
     res:`[Burp Suite] Intercepting login POST request...\n[+] Injecting: user_id=1 UNION SELECT NULL,user,pass,NULL--\n[+] Response leaks: admin:$2y$10$eHrGKm3... (bcrypt hash)\n[+] Second payload: extracting all 47 user records\n[+] Zero WAF hits — requests look organic.\n[+] Bonus: found /admin panel path in page source.\nElite technique. Surgical. Zero detection. Clean.`,rt:'good'},
    {lbl:'> spray default credentials (admin/admin, admin/password)',desc:'Quick check before going technical',tag:'LOW EFFORT',tc:'ta',ad:6,pts:40,
     res:`[hydra] Testing 15 common credential pairs...\n[-] admin:admin — FAILED\n[-] admin:password123 — FAILED\n[-] administrator:Welcome1 — FAILED\n[-] root:toor — FAILED\n[+] Useful: no account lockout policy detected\n[!] No access gained. 8 minutes wasted.\n[~] Credential spray rarely works on well-configured apps.`,rt:'bad'},
   ]},
  {id:'03',name:'ROOT ACCESS',target:'web-server-01 — Post-Exploitation (www-data shell)',
   tools:['LinPEAS','Metasploit','Manual enum'],
   brief:`STATUS: Shell acquired as www-data on web-server-01.\nKERNEL: Linux web01 4.15.0-76 #86 SMP x86_64\n\nYou're in — but limited. Need root to read /etc/shadow\nand demonstrate full compromise for the pentest report.\n\nEDR is running. Security team resumes monitoring in ~10min.\nMake it count. Make it quiet.\n\nPrivilege escalation method?`,
   opts:[
    {lbl:'> searchsploit kernel 4.15 → compile CVE-2021-4034',desc:'Kernel exploit (PwnKit) — powerful but destabilizing',tag:'RISKY',tc:'tr',ad:52,pts:140,
     res:`[*] Fetching PwnKit exploit (CVE-2021-4034)...\n[*] Compiling payload... done.\n[*] Executing pkexec exploit...\n[+] uid=0(root) gid=0(root) — ROOT OBTAINED\n[!] ALERT: Kernel panic entry written to syslog\n[!] EDR flagged anomalous pkexec invocation\n[!] Auditd logged privilege escalation event\n[~] Root obtained. System partially destabilized. Messy.`,rt:'warn'},
    {lbl:'> find / -perm -4000 2>/dev/null → exploit SUID binary',desc:'Manual SUID enumeration — precise, leaves no artifacts',tag:'OPTIMAL',tc:'tg',ad:7,pts:195,
     res:`[*] Enumerating SUID binaries silently...\n[+] /usr/bin/find — SUID bit set (misconfigured!)\n[+] Running: find . -exec /bin/bash -p \\;\n[+] bash-4.4# whoami → root\n[+] Confirmed: full root access.\n[+] /etc/shadow extracted: 47 credential hashes.\n[+] Zero logs. Zero EDR hits. Zero artifacts.\nGhost mode. Masterful. Untraceable.`,rt:'good'},
    {lbl:'> upload & run linpeas.sh (automated priv-esc audit)',desc:'Automated scanner — thorough but leaves /tmp artifacts',tag:'MODERATE',tc:'ta',ad:20,pts:160,
     res:`[*] Downloading linpeas.sh via wget to /tmp...\n[+] Running enumeration suite...\n[+] CRITICAL: /opt/backup.sh world-writable (cron runs as root)\n[+] Injecting reverse shell payload into backup.sh\n[*] Waiting for cron execution (4m 30s)...\n[+] Root shell received on port 4444!\n[!] AIDE detected new file: /tmp/linpeas.sh\n[~] Root obtained. Traces in /tmp. Acceptable for a pentest.`,rt:'good'},
   ]},
];

function alertColor(a){return a<40?'#00ff41':a<72?'#ffb700':'#ff5555'}

function initMatrix(){
  const c=$('mc'),ctx=c.getContext('2d'),p=$('g');
  c.width=p.offsetWidth||680;c.height=p.offsetHeight||680;
  const cols=Math.floor(c.width/13),drops=Array(cols).fill(1);
  const chars='01アイウエオHACKEXPLOIT{}[];netcat>nmap<SYN0110';
  setInterval(()=>{
    ctx.fillStyle='rgba(5,10,5,.07)';ctx.fillRect(0,0,c.width,c.height);
    ctx.fillStyle='#00ff41';ctx.font='11px Courier New';
    drops.forEach((y,i)=>{
      ctx.fillText(chars[Math.floor(Math.random()*chars.length)],i*13,y*13);
      if(y*13>c.height&&Math.random()>.975)drops[i]=0;
      drops[i]++;
    });
  },60);
}

function typewrite(el,txt,spd=16){
  return new Promise(r=>{
    el.textContent='';let i=0;
    const t=setInterval(()=>{
      if(txt[i]==='\n'){const br=document.createElement('br');el.appendChild(br);}
      else{el.appendChild(document.createTextNode(txt[i]));}
      i++;if(i>=txt.length){clearInterval(t);r();}
    },spd);
  });
}

function hudHTML(){
  const ac=alertColor(G.alert);
  return `<div class="hud">
    <div><div class="hl">OPERATOR</div><div class="hv">FAWAD.MIR</div></div>
    <div><div class="hl">MISSION</div><div class="hv">${String(G.mission+1).padStart(2,'0')} / 03</div></div>
    <div style="text-align:right">
      <div class="hl">ALERT LEVEL</div>
      <div class="hv" style="color:${ac}">${G.alert}%</div>
      <div class="abar"><div class="afill" id="af" style="width:${G.alert}%;background:${ac}"></div></div>
    </div>
    <div style="text-align:right"><div class="hl">SCORE</div><div class="hv">${G.score}</div></div>
  </div>`;
}

function showSplash(){
  sc.innerHTML=`<div class="scr" style="justify-content:center;align-items:center;text-align:center">
    <div style="margin-bottom:4px;animation:pulse 2s infinite">
      <div class="dim" style="margin-bottom:28px;letter-spacing:6px">◈ CLASSIFIED OPERATION ◈</div>
      <div class="big-title" style="font-size:52px;letter-spacing:14px">OPERATOR</div>
      <div style="font-size:16px;letter-spacing:8px;color:rgba(0,200,51,.8);margin:6px 0 4px">RED CELL</div>
      <div class="dim">A HACKING RPG</div>
    </div>
    <div style="width:220px;height:1px;background:rgba(0,255,65,.4);margin:28px auto"></div>
    <div style="font-size:12px;color:rgba(0,136,34,.7);letter-spacing:2px;line-height:2;margin-bottom:40px">
      FEATURING REAL TOOLS: NMAP · BURP SUITE · SQLMAP<br>METASPLOIT · LINPEAS · SCANIBAL · WEBHAWK
    </div>
    <button class="pbtn vis" onclick="startGame()">[ INITIALIZE OPERATOR ]</button>
    <div style="margin-top:40px;font-size:11px;color:rgba(0,51,9,.9);letter-spacing:2px;line-height:1.9">
      Based on the arsenal of FAWAD AHMED MIR<br>
      Penetration Tester · Security Researcher<br>
      <span style="color:rgba(0,51,9,.6)">⚠ ALL TECHNIQUES FOR EDUCATIONAL USE ONLY</span>
    </div>
  </div>`;
}

function showBriefing(){
  const m=MS[G.mission];
  sc.innerHTML=`<div class="scr">
    ${hudHTML()}
    <div class="dim" style="margin-bottom:12px">◈ SECURE CHANNEL ESTABLISHED ◈</div>
    <div style="margin-bottom:16px">
      <div class="dim" style="margin-bottom:6px">MISSION ${m.id} OF 03</div>
      <div class="big-title" style="font-size:30px;letter-spacing:6px">${m.name}</div>
    </div>
    <div class="dim" style="margin-bottom:6px">TARGET SYSTEM</div>
    <div style="border:1px solid rgba(0,255,65,.2);padding:8px 12px;font-size:12px;color:rgba(0,200,51,.9);border-radius:4px;margin-bottom:14px">${m.target}</div>
    <div class="dim" style="margin-bottom:6px">AVAILABLE TOOLS</div>
    <div style="margin-bottom:16px">${m.tools.map(t=>`<span class="tag tg">${t}</span>`).join('')}</div>
    <div class="dim" style="margin-bottom:6px">MISSION BRIEFING</div>
    <div class="narr" id="bt" style="min-height:155px"></div>
    <div style="margin-top:auto;padding-top:20px">
      <button class="pbtn" id="bb" onclick="showMission()">[ BEGIN OPERATION ${m.id} ]</button>
    </div>
  </div>`;
  typewrite($('bt'),MS[G.mission].brief,14).then(()=>{$('bb').classList.add('vis')});
}

function showMission(){
  const m=MS[G.mission];
  sc.innerHTML=`<div class="scr">
    ${hudHTML()}
    <div class="dim" style="margin-bottom:4px">◈ ${m.name} — LIVE ◈</div>
    <div style="font-size:12px;color:rgba(0,136,34,.8);margin-bottom:16px">${m.target}</div>
    <div class="narr" id="ml" style="min-height:72px;font-size:13px">
      <span class="log-ok">┌─[fawad㉿redcell]-[~/${m.name.toLowerCase().replace(/ /g,'_')}]</span><br>
      <span class="log-ok">└─$ </span><span id="mc2" class="cursor-blink"></span>
    </div>
    <div class="dim" style="margin-bottom:8px;margin-top:8px">SELECT APPROACH</div>
    <div class="choices" id="ca" style="display:none">
      ${m.opts.map((o,i)=>`<button class="cbtn" onclick="pickOpt(${i})">
        <div style="display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:4px">
          <span>${o.lbl}</span><span class="tag ${o.tc}">${o.tag}</span>
        </div>
        <div class="cbtn-desc">${o.desc}</div>
      </button>`).join('')}
    </div>
  </div>`;
  typewrite($('mc2'),`connecting to ${m.target.split('—')[0].trim().toLowerCase()}...`,38).then(()=>{
    setTimeout(()=>{
      $('ca').style.display='flex';
      $('mc2').classList.remove('cursor-blink');
      $('mc2').textContent='awaiting operator command_';
      $('mc2').style.color='#ffb700';
    },700);
  });
}

function pickOpt(idx){
  const m=MS[G.mission];
  const o=m.opts[idx];
  G.choices.push({mi:G.mission,oi:idx,tag:o.tag});
  G.alert=Math.min(100,G.alert+o.ad);
  document.querySelectorAll('.cbtn').forEach(b=>b.disabled=true);
  if(G.alert>=100){showGameOver('ALERT THRESHOLD BREACHED — OPERATION BURNED');return;}
  const pts=o.ad>35?Math.round(o.pts*.82):o.pts;
  G.score+=pts;
  showResult(o,pts);
}

function showResult(o,pts){
  const ac=alertColor(G.alert);
  const isLast=G.mission>=MS.length-1;
  sc.innerHTML=`<div class="scr">
    ${hudHTML()}
    <div class="dim" style="margin-bottom:4px">◈ EXECUTING: ${o.tag} ◈</div>
    <div style="font-size:12px;color:rgba(0,136,34,.8);margin-bottom:4px">${o.lbl}</div>
    <div class="pbar"><div class="pfill" id="pf"></div></div>
    <div class="narr" id="rl" style="min-height:160px;font-size:12.5px"></div>
    <div class="g2" id="rs" style="display:none;margin-top:14px">
      <div class="rcard">
        <div class="l" style="font-size:10px;color:rgba(0,136,34,.8);letter-spacing:2px">POINTS</div>
        <div style="font-size:26px;color:#00ff41;margin-top:4px">+${pts}</div>
      </div>
      <div class="rcard ${o.ad>30?'rcard-r':''}">
        <div class="l" style="font-size:10px;color:rgba(0,136,34,.8);letter-spacing:2px">ALERT RAISED</div>
        <div style="font-size:26px;color:${ac};margin-top:4px">+${o.ad}%</div>
      </div>
    </div>
    <div style="margin-top:auto;padding-top:16px">
      <button class="pbtn" id="nb" onclick="${isLast?'showEndgame()':'nextMission()'}">${isLast?'[ GENERATE FINAL REPORT ]':'[ PROCEED TO MISSION '+String(G.mission+2).padStart(2,'0')+' ]'}</button>
    </div>
  </div>`;
  setTimeout(()=>{if($('pf'))$('pf').style.width='100%'},50);
  setTimeout(()=>{
    const rl=$('rl');
    typewrite(rl,o.res,17).then(()=>{
      $('rs').style.display='grid';
      $('nb').classList.add('vis');
    });
  },2100);
}

function nextMission(){G.mission++;showBriefing();}

function showGameOver(reason){
  sc.innerHTML=`<div class="scr" style="justify-content:center;align-items:center;text-align:center">
    <div class="dim" style="color:rgba(255,49,49,.7);letter-spacing:4px;margin-bottom:14px">◈ OPERATION COMPROMISED ◈</div>
    <div class="big-title" style="color:#ff5555;font-size:38px;letter-spacing:8px">ACCESS DENIED</div>
    <div style="width:200px;height:1px;background:rgba(255,49,49,.4);margin:20px auto"></div>
    <div style="font-size:13px;color:#ff5555;margin-bottom:6px">${reason}</div>
    <div style="font-size:11px;color:rgba(136,34,34,.9);letter-spacing:2px;margin-bottom:36px">SECURITY TEAM CONVERGING — ABORT ABORT ABORT</div>
    <div class="g2" style="max-width:280px;margin:0 auto 28px">
      <div class="sbox"><div class="l">FINAL SCORE</div><div class="n" style="color:#ff5555">${G.score}</div></div>
      <div class="sbox"><div class="l">MISSIONS</div><div class="n" style="color:#ff5555">${G.mission}/3</div></div>
    </div>
    <button class="pbtn vis" style="border-color:#ff5555;color:#ff5555" onclick="resetGame()">[ REINITIALIZE — TRY AGAIN ]</button>
    <div style="margin-top:20px;font-size:11px;color:rgba(68,17,17,.9);letter-spacing:2px">TIP: LOWER ALERT = BETTER OPERATOR</div>
  </div>`;
}

function showEndgame(){
  const sb=Math.max(0,Math.round((100-G.alert)*2.8));
  const final=G.score+sb;
  let gr,gc,gt;
  if(final>=700){gr='S';gc='#00ff41';gt='GHOST OPERATOR'}
  else if(final>=540){gr='A';gc='#44ff88';gt='ELITE HACKER'}
  else if(final>=380){gr='B';gc='#ffb700';gt='SKILLED TESTER'}
  else if(final>=230){gr='C';gc='#ff8800';gt='APPRENTICE'}
  else{gr='D';gc='#ff5555';gt='NEEDS PRACTICE'}
  const opt=G.choices.filter(c=>MS[c.mi].opts[c.oi].tag==='OPTIMAL').length;
  sc.innerHTML=`<div class="scr">
    <div class="dim" style="text-align:center;margin-bottom:16px;letter-spacing:4px">◈ OPERATION DEBRIEF — CLASSIFIED ◈</div>
    <div style="text-align:center;margin-bottom:4px">
      <div style="font-size:60px;color:${gc};letter-spacing:4px;line-height:1">${gr}</div>
      <div style="font-size:13px;letter-spacing:5px;color:${gc};margin-top:6px">${gt}</div>
    </div>
    <div style="font-size:40px;color:#00ff41;letter-spacing:6px;text-align:center;margin:12px 0">${final} <span style="font-size:14px;color:rgba(0,136,34,.8)">PTS</span></div>
    <hr class="sep">
    <div class="g2">
      <div class="sbox"><div class="l">BASE SCORE</div><div class="n">${G.score}</div></div>
      <div class="sbox"><div class="l">STEALTH BONUS</div><div class="n" style="color:#44ff88">+${sb}</div></div>
      <div class="sbox"><div class="l">FINAL ALERT</div><div class="n" style="color:${alertColor(G.alert)}">${G.alert}%</div></div>
      <div class="sbox"><div class="l">OPTIMAL PLAYS</div><div class="n">${opt} / 3</div></div>
    </div>
    <hr class="sep">
    <div class="dim" style="margin-bottom:10px">DECISION LOG</div>
    <div style="font-size:12px;line-height:2">
      ${G.choices.map(c=>{
        const m=MS[c.mi],o=m.opts[c.oi];
        const ic=o.tag==='OPTIMAL'?'✓':o.ad>35?'✗':'~';
        const cl=o.tag==='OPTIMAL'?'log-ok':o.ad>35?'log-err':'log-warn';
        return `<div class="${cl}">[${ic}] MISSION ${m.id}: ${o.lbl.slice(2,44)}... — ${o.tag}</div>`;
      }).join('')}
    </div>
    <hr class="sep">
    <div class="dim" style="margin-bottom:8px">TOOLS DEPLOYED</div>
    <div style="margin-bottom:20px">${[...new Set(G.choices.flatMap(c=>MS[c.mi].tools))].map(t=>`<span class="tag tg">${t}</span>`).join('')}</div>
    <div style="display:flex;gap:8px;flex-wrap:wrap">
      <button class="pbtn vis" onclick="resetGame()" style="flex:1">[ RUN AGAIN ]</button>
      <button class="pbtn vis" onclick="openLink('https://github.com/notfawadmir')" style="flex:1;font-size:11px">[ FAWAD'S GITHUB ↗ ]</button>
    </div>
    <div style="margin-top:14px;text-align:center;font-size:10px;color:rgba(0,51,9,.8);letter-spacing:2px">
      REAL TECHNIQUES · ETHICAL HACKING · HACK LEGALLY · HACK THE PLANET
    </div>
  </div>`;
}

function startGame(){G.alert=0;G.score=0;G.mission=0;G.choices=[];showBriefing();}
function resetGame(){G.alert=0;G.score=0;G.mission=0;G.choices=[];showSplash();}

showSplash();
initMatrix();
</script>
