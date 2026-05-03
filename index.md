---
layout: default
permalink: /
---

<div class="body">
  <div class="left">
    <div class="bio" id="bio">
      <p>I am a PhD student at the <a href="https://vectorinstitute.ai/">Vector Institute</a> and the University of Calgary, supervised by <a href="https://yani.ai/">Dr. Yani Ioannou</a> and <a href="https://www.cs.toronto.edu/~rahulgk/">Dr. Rahul Krishnan</a>.</p>
      <p>My research focuses on making large foundational models — such as LLMs — smaller and more efficient, through sparse neural network training, training dynamics, and loss landscape geometry.</p>
      <p>Supported by NSERC, Borealis AI, DRAC, and the Killam Fellowship. Feel free to reach out to discuss or collaborate.</p>
    </div>

    <div class="research-block">
      <div class="section-label">Research Interests</div>
      {% for rq in site.data.research %}
      <div class="rq-item">
        <div class="rq-trigger" onclick="toggle(this)">
          <span class="rq-title">{{ rq.question }}</span>
          <svg class="rq-arrow" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5"><polyline points="5,3 11,8 5,13"/></svg>
        </div>
        <div class="rq-body">{{ rq.answer }}</div>
      </div>
      {% endfor %}
    </div>

    <div class="updates-wrap" id="updates">
      <div class="updates-label">Updates</div>
      <div class="updates-scroll">
        {% for update in site.data.updates %}
        <div class="update-row">
          <span class="upd-date">{{ update.date }}</span>
          <span class="upd-text">{{ update.text }}</span>
        </div>
        {% endfor %}
      </div>
    </div>
  </div>

  <div class="sidebar">
    <img class="profile-photo" src="{{ site.author.photo | relative_url }}" alt="{{ site.author.name }}" />
    <div class="profile-name">{{ site.author.name }}</div>
    <div class="icon-row">
      <a class="icon-link" href="mailto:{{ site.author.email }}" title="Email">
        <svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.4"><rect x="1" y="3" width="14" height="10" rx="1.2"/><polyline points="1,4 8,9.5 15,4"/></svg>
      </a>
      <a class="icon-link" href="{{ site.author.linkedin }}" target="_blank" title="LinkedIn">
        <svg viewBox="0 0 16 16" fill="currentColor"><path d="M0 1.146C0 .513.526 0 1.175 0h13.65C15.474 0 16 .513 16 1.146v13.708c0 .633-.526 1.146-1.175 1.146H1.175C.526 16 0 15.487 0 14.854V1.146zm4.943 12.248V6.169H2.542v7.225h2.401zm-1.2-8.212c.837 0 1.358-.554 1.358-1.248-.015-.709-.52-1.248-1.342-1.248-.822 0-1.359.54-1.359 1.248 0 .694.521 1.248 1.327 1.248h.016zm4.908 8.212V9.359c0-.216.016-.432.08-.586.173-.431.568-.878 1.232-.878.869 0 1.216.662 1.216 1.634v3.865h2.401V9.25c0-2.22-1.184-3.252-2.764-3.252-1.274 0-1.845.7-2.165 1.193v.025h-.016a5.54 5.54 0 01.016-.025V6.169h-2.4c.03.678 0 7.225 0 7.225h2.4z"/></svg>
      </a>
      <a class="icon-link" href="{{ site.author.github }}" target="_blank" title="GitHub">
        <svg viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
      </a>
      <a class="icon-link" href="{{ site.author.scholar }}" target="_blank" title="Google Scholar">
        <svg viewBox="0 0 16 16" fill="currentColor"><path d="M7.5 1L0 5.5l2.5 1.5V11c0 1.38 2.24 2.5 5 2.5s5-1.12 5-2.5V7l1.5-.9V11.5H15V5.5L7.5 1zM7.5 12C5.57 12 4 11.33 4 10.5S5.57 9 7.5 9 11 9.67 11 10.5 9.43 12 7.5 12z"/></svg>
      </a>
    </div>
  </div>
</div>
