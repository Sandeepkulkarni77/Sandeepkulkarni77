<!DOCTYPE html>
<html>
<head>
<style>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700;900&family=Share+Tech+Mono&display=swap');
*{margin:0;padding:0;box-sizing:border-box;}
body{background:#020408;font-family:'Share Tech Mono',monospace;color:#cdd9e5;}

.bg{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:0;
  background-image:linear-gradient(rgba(0,255,136,0.03) 1px,transparent 1px),linear-gradient(90deg,rgba(0,255,136,0.03) 1px,transparent 1px);
  background-size:40px 40px;animation:bgpulse 8s ease-in-out infinite alternate;}
@keyframes bgpulse{from{opacity:0.5}to{opacity:1}}

.page{position:relative;z-index:2;max-width:700px;margin:0 auto;padding:16px;}

.hdr{border:1px solid #00ff8844;border-radius:18px;padding:36px 24px 26px;margin-bottom:14px;position:relative;overflow:hidden;background:radial-gradient(ellipse at 50% 0%,rgba(0,255,136,.04) 0%,transparent 70%);}
.hdr .scan{position:absolute;top:0;left:-40%;width:40%;height:100%;background:linear-gradient(90deg,transparent,rgba(0,255,136,.04),transparent);animation:scanswp 3.5s ease-in-out infinite;}
@keyframes scanswp{0%{left:-40%}100%{left:140%}}

.name{
  font-family:'Orbitron',sans-serif;
  font-size:22px;
  font-weight:900;
  text-align:center;
  min-height:36px;
  letter-spacing:.04em;
  color:#00ff88;
  -webkit-text-stroke:0;
  text-shadow:none;
}

.cur{display:inline-block;width:2px;height:.85em;background:#00ff88;vertical-align:middle;animation:blink .65s step-end infinite;}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

.div{height:1px;margin:0 0 14px;background:linear-gradient(to right,transparent,#00ff8866,#00d4ff55,transparent);}

.card{background:#080f1a;border:1px solid #1a2a3a;border-radius:14px;padding:20px 20px 16px;margin-bottom:14px;position:relative;overflow:hidden;}
.card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(to right,transparent,var(--ac),transparent);}
.card[data-ac="green"]{--ac:#00ff88;}
.card[data-ac="blue"]{--ac:#00d4ff;}
.card[data-ac="pink"]{--ac:#ff79c6;}
.card-title{font-family:'Orbitron',sans-serif;font-size:12px;font-weight:700;letter-spacing:.12em;text-transform:uppercase;margin-bottom:14px;display:flex;align-items:center;gap:8px;}
.card-title span{color:var(--ac);text-shadow:0 0 8px var(--ac);}
.about-item{display:flex;align-items:flex-start;gap:10px;font-size:11.5px;line-height:1.75;color:#8a9bb0;margin-bottom:6px;}
.about-item .tag{color:#00ff88;flex-shrink:0;}
.about-item b{color:#cdd9e5;}
.bg-group{margin-bottom:16px;}
.bg-group:last-child{margin-bottom:0;}
.bg-label{font-size:9px;letter-spacing:.15em;color:#3a5a4a;text-transform:uppercase;margin-bottom:8px;}
.badges{display:flex;flex-wrap:wrap;gap:7px;}
.badge{display:flex;align-items:center;gap:7px;font-size:10px;font-weight:700;letter-spacing:.06em;padding:6px 12px;border-radius:8px;border:1px solid;cursor:default;transition:transform .15s,box-shadow .15s;}
.badge:hover{transform:translateY(-3px) scale(1.05);}
.badge img{width:15px;height:15px;object-fit:contain;flex-shrink:0;}
.badge .ico{width:15px;height:15px;flex-shrink:0;display:flex;align-items:center;justify-content:center;font-size:14px;line-height:1;}
.b-g{color:#00ff88;border-color:#00ff8844;background:#001a0e;} .b-g:hover{box-shadow:0 4px 16px #00ff8844;}
.b-b{color:#00d4ff;border-color:#00d4ff44;background:#00111a;} .b-b:hover{box-shadow:0 4px 16px #00d4ff44;}
.b-p{color:#c084fc;border-color:#c084fc44;background:#0e0020;} .b-p:hover{box-shadow:0 4px 16px #c084fc44;}
.b-o{color:#ffb86c;border-color:#ffb86c44;background:#1a0e00;} .b-o:hover{box-shadow:0 4px 16px #ffb86c44;}
.b-r{color:#ff5555;border-color:#ff555544;background:#1a0000;} .b-r:hover{box-shadow:0 4px 16px #ff555544;}
.b-cy{color:#00ffee;border-color:#00ffee44;background:#001a18;} .b-cy:hover{box-shadow:0 4px 16px #00ffee44;}
.b-y{color:#f1e05a;border-color:#f1e05a44;background:#1a1800;} .b-y:hover{box-shadow:0 4px 16px #f1e05a44;}
.b-pu{color:#c084fc;border-color:#c084fc44;background:#0e0020;} .b-pu:hover{box-shadow:0 4px 16px #c084fc44;}
.contact-row{display:flex;align-items:center;gap:10px;font-size:12px;color:#5a7a8a;margin-bottom:10px;}
.contact-row:last-child{margin-bottom:0;}
.contact-row a{color:#00d4ff;text-decoration:none;transition:color .2s;}
.contact-row a:hover{color:#00ff88;}
.footer{text-align:center;font-size:10px;color:#1e3a2f;letter-spacing:.1em;padding-top:8px;}
.pulse-dot{display:inline-block;width:7px;height:7px;border-radius:50%;background:#00ff88;margin-right:5px;vertical-align:middle;animation:pulseA 2s ease infinite;}
@keyframes pulseA{0%,100%{box-shadow:0 0 0 0 #00ff8866}50%{box-shadow:0 0 0 6px transparent}}
</style>
</head>
<body>

<div class="bg"></div>
<div class="page">

  <div class="hdr">
    <div class="scan"></div>
    <div class="name"><span id="tw"></span><span class="cur"></span></div>
  </div>

  <div class="div"></div>

  <div class="card" data-ac="green">
    <div class="card-title"><span>🚀 About Me</span></div>
    <div class="about-item"><span class="tag">›</span><span>🎯 Focused on <b>DevOps / Cloud Engineering</b></span></div>
    <div class="about-item"><span class="tag">›</span><span>🔥 Upskilling in <b>Linux, Shell Scripting, Docker, Kubernetes, Jenkins, GitHub Actions, GitOps Practices, Ansible, Prometheus, Grafana, AWS & Terraform</b></span></div>
    <div class="about-item"><span class="tag">›</span><span>📌 Building systems that are <b>reliable, scalable & production-ready</b></span></div>
  </div>

  <div class="card" data-ac="blue">
    <div class="card-title"><span>🛠️ Tech Stack</span></div>
    <div class="bg-group">
      <div class="bg-label">⚙️ DevOps &amp; Cloud</div>
      <div class="badges">
        <span class="badge b-g"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg"/>LINUX</span>
        <span class="badge b-g">
          <svg width="15" height="15" viewBox="0 0 24 24"><rect x="3" y="4" width="18" height="2" rx="1" fill="#00ff88"/><rect x="3" y="9" width="13" height="2" rx="1" fill="#00ff88"/><rect x="3" y="14" width="16" height="2" rx="1" fill="#00ff88"/><rect x="3" y="19" width="10" height="2" rx="1" fill="#00ff88"/></svg>
          SHELL SCRIPTING
        </span>
        <span class="badge b-b"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg"/>DOCKER</span>
        <span class="badge b-b"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kubernetes/kubernetes-plain.svg"/>KUBERNETES</span>
        <span class="badge b-r"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jenkins/jenkins-original.svg"/>JENKINS</span>
        <span class="badge b-p"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" style="filter:invert(1) sepia(1) saturate(3) hue-rotate(240deg)"/>GITHUB ACTIONS</span>
        <span class="badge b-cy">
          <svg width="15" height="15" viewBox="0 0 24 24"><circle cx="12" cy="12" r="3" fill="#00ffee"/><path d="M12 2v4M12 18v4M2 12h4M18 12h4M5.6 5.6l2.8 2.8M15.6 15.6l2.8 2.8M5.6 18.4l2.8-2.8M15.6 8.4l2.8-2.8" stroke="#00ffee" stroke-width="1.5" stroke-linecap="round"/></svg>
          GITOPS PRACTICES
        </span>
        <span class="badge b-o"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/ansible/ansible-original.svg"/>ANSIBLE</span>
        <span class="badge b-r"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/prometheus/prometheus-original.svg"/>PROMETHEUS</span>
        <span class="badge b-o"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/grafana/grafana-original.svg"/>GRAFANA</span>
        <span class="badge b-y"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" style="filter:brightness(0) saturate(100%) invert(85%) sepia(60%) saturate(400%) hue-rotate(5deg)"/>AWS</span>
        <span class="badge b-pu"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/terraform/terraform-original.svg"/>TERRAFORM</span>
      </div>
    </div>
    <div class="bg-group">
      <div class="bg-label">🧩 Programming</div>
      <div class="badges">
        <span class="badge b-b"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg"/>PYTHON</span>
      </div>
    </div>
    <div class="bg-group">
      <div class="bg-label">🔧 Tools</div>
      <div class="badges">
        <span class="badge b-r"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg"/>GIT</span>
        <span class="badge b-p"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" style="filter:invert(1) sepia(1) saturate(3) hue-rotate(240deg)"/>GITHUB</span>
      </div>
    </div>
  </div>

  <div class="card" data-ac="pink">
    <div class="card-title"><span>📬 Contact</span></div>
    <div class="contact-row">📧 <a href="mailto:sandeepkulkarni2003@gmail.com">sandeepkulkarni2003@gmail.com</a></div>
    <div class="contact-row">📞 <a href="tel:+918971748386">+91 8971748386</a></div>
    <div class="contact-row">🔗 <a href="https://www.linkedin.com/in/sandeep-kulkarni-b8a69a29a/" target="_blank">linkedin.com/in/sandeep-kulkarni</a></div>
  </div>

  <div class="footer">
    <span class="pulse-dot"></span>
    OPEN TO OPPORTUNITIES &nbsp;·&nbsp; github.com/Sandeepkulkarni77
  </div>
</div>

<script>
const tw=document.getElementById('tw');
const phrases=["Hello, I'm Sandeep Kulkarni","Welcome to my GitHub Profile"];
let pi=0,ci=0,del=false,hold=0;
function tick(){
  if(hold>0){hold--;setTimeout(tick,60);return;}
  const p=phrases[pi];
  if(!del){
    tw.textContent=p.slice(0,++ci);
    if(ci===p.length){hold=22;del=true;}
    setTimeout(tick,55);
  } else {
    tw.textContent=p.slice(0,--ci);
    if(ci===0){del=false;pi=(pi+1)%phrases.length;hold=8;}
    setTimeout(tick,28);
  }
}
tick();
</script>

</body>
</html>



