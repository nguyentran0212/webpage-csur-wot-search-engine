---
layout: default
title: "Searching the Web of Things — State of the Art, Challenges, and Solutions"
description: "A systematic survey of over 200 Web of Things search-engine works, introducing a meta-path conceptual model and a modular reference architecture for WoTSE."
---

<section class="hero">
  <div class="hero-inner">
    <p class="venue-badge">
      <span class="venue-name">ACM Computing Surveys</span>
      <span class="venue-sep">·</span>
      <span>Vol. 50</span>
      <span class="venue-sep">·</span>
      <span>No. 4</span>
      <span class="venue-sep">·</span>
      <span>pp. 1–34</span>
      <span class="venue-sep">·</span>
      <span>2017</span>
    </p>

    <h1 class="paper-title">Searching the Web of Things</h1>
    <p class="paper-subtitle">State of the Art, Challenges, and Solutions</p>

    <p class="authors">
      <span><strong>Nguyen Khoi Tran</strong><sup>1</sup></span>
      <span class="dot">·</span>
      <span><strong>Quan Z. Sheng</strong><sup>2</sup></span>
      <span class="dot">·</span>
      <span><strong>Muhammad Ali Babar</strong><sup>1</sup></span>
      <span class="dot">·</span>
      <span><strong>Lina Yao</strong><sup>3</sup></span>
    </p>

    <p class="affiliations">
      <sup>1</sup> The University of Adelaide, Australia &nbsp;
      <sup>2</sup> Macquarie University, Australia &nbsp;
      <sup>3</sup> The University of New South Wales, Australia
    </p>

    <div class="hero-actions">
      <a class="btn btn-primary" href="{{ '/assets/pdf/CSUR_WoTSE_NguyenTran.pdf' | relative_url }}">⬇ Download PDF</a>
      <a class="btn btn-ghost" href="https://doi.org/10.1145/3092695" rel="noopener">View on ACM Digital Library ↗</a>
    </div>
  </div>
</section>

<section class="section section--alt">
  <div class="container">
    <h2>TL;DR</h2>
    <p>
      The Web of Things turns physical objects into addressable Web resources — sensor streams,
      actuation services, metadata pages. Search engines are the librarians of that emerging
      library. This survey analyses <strong>over 200 academic works</strong> on
      <em>Web of Things Search Engines (WoTSE)</em> and introduces a
      <strong>meta-path</strong> conceptual model and a <strong>modular reference architecture</strong>
      that together describe the diversity of WoTSE forms. The models are operationalised into a
      <strong>24-dimension analytical framework</strong> used to review the growth and current state of
      the field, illustrated through <strong>30 representative prototypes</strong>.
    </p>
  </div>
</section>

<section class="section">
  <div class="container">
    <h2>At a glance</h2>
    <div class="stat-grid">
      <div class="stat">
        <div class="stat-value">200+</div>
        <div class="stat-label">academic works analysed</div>
      </div>
      <div class="stat">
        <div class="stat-value">30</div>
        <div class="stat-label">representative prototypes reviewed</div>
      </div>
      <div class="stat">
        <div class="stat-value">24</div>
        <div class="stat-label">analytical dimensions</div>
      </div>
      <div class="stat">
        <div class="stat-value">7</div>
        <div class="stat-label">dimension groups</div>
      </div>
    </div>
  </div>
</section>

<section class="section section--alt">
  <div class="container">
    <h2>The motivation</h2>
    <p>
      The World Wide Web is being extended to physical objects. Each object exposes a
      digital counterpart (a Web Thing) accessible over HTTP, with JSON or HTML
      representations and RESTful APIs. Applications no longer hard-code which lamp,
      thermometer, or location service they talk to; they query a search engine that
      <em>discovers</em> resources in a given scope and returns the ones that match.
    </p>
    <p>
      Consider a smart-home application that needs to blink the lamp closest to the house
      owner when the meal in the oven reaches its target temperature. It needs the right
      lamp, a meat-thermometer stream, an indoor-localisation stream, and a temperature
      reference service. A WoT search engine decouples resource retrieval from application
      logic: as long as the application can talk to a search engine covering its scope,
      it can configure itself and stay up-to-date as resources change.
    </p>
    <figure class="figure">
      <img src="{{ '/assets/figures/application.png' | relative_url }}" alt="Search engines acting as middle-ware between applications and Web of Things resources">
      <figcaption>
        Search engines as middle-ware between applications and Web of Things resources.
      </figcaption>
    </figure>
  </div>
</section>

<section class="section">
  <div class="container">
    <h2>Two contributions: a model and an architecture</h2>
    <p>
      WoTSE in the literature look very different. Some locate RFID-tagged objects in a room,
      others index streaming sensor data, others expose semantic descriptions of physical
      functionalities. To capture this diversity, the survey introduces two complementary
      abstractions:
    </p>
    <ul class="framework-list">
      <li><strong>Meta-path</strong>: the signature of a WoTSE. Describes the types of resources used to assess a query, the chain of objects linking them, and the resources used to build results.</li>
      <li><strong>Modular architecture</strong>: a layered reference architecture (Discovery, Index, Search, UI) plus a vertical Security/Privacy/Trust layer that any WoTSE can be decomposed into.</li>
    </ul>

    <figure class="figure">
      <img src="{{ '/assets/figures/Metapath.png' | relative_url }}" alt="The Meta-path model illustrated with a query for available meeting rooms">
      <figcaption>
        The Meta-path model illustrated with a query for available meeting rooms in a smart building.
        Query resources (sensor streams + metadata) are linked to result resources (room pages) through
        a chain of objects.
      </figcaption>
    </figure>

    <figure class="figure">
      <img src="{{ '/assets/figures/Architecture.png' | relative_url }}" alt="The modular reference architecture for Web of Things Search Engines">
      <figcaption>
        The modular reference architecture: Discovery and Index layers below; Search and UI layers above;
        Security, Privacy and Trust span the system as a vertical layer.
      </figcaption>
    </figure>
  </div>
</section>

<section class="section section--alt">
  <div class="container">
    <h2>Research method</h2>
    <p>
      The survey starts from the DBLP and Scopus bibliographic corpora. A semi-automated
      selection algorithm filters candidates that mention search/discovery/query keywords
      and are tied to WoT/IoT venues; highly cited references from the candidates are then
      folded back into the candidate pool. From an initial pool of over 200 works, the
      authors manually select <strong>30 representative prototypes</strong> for fine-grained
      analysis, balancing highly cited "classical" works with the latest contributions.
      Each prototype is mapped onto <strong>24 dimensions</strong> organised into seven groups,
      covering meta-path, scope, discovery, indexing, query processing, user interface,
      security, and evaluation.
    </p>
    <figure class="figure">
      <img src="{{ '/assets/figures/AnalyticalFramework.png' | relative_url }}" alt="Overview of the analytical framework">
      <figcaption>
        Overview of the analytical framework. Ovals mark components built by the authors; solid arrows
        show data flow from bibliographic inputs to the comparison tables.
      </figcaption>
    </figure>
  </div>
</section>

<section class="section">
  <div class="container">
    <h2>What the literature is actually doing</h2>
    <p>Here are some of the patterns the survey surfaces across the 30 prototypes.</p>

    <div class="finding">
      <h3>Most common forms of WoT search</h3>
      <div class="finding-grid">
        <div class="finding-item"><span class="num">R → R</span><span class="lbl">finding objects by <strong>ID or metadata</strong> (the dominant form)</span></div>
        <div class="finding-item"><span class="num">R + D → Obj → R</span><span class="lbl">finding objects by their <strong>real-time state</strong> (for example, sensor readings)</span></div>
        <div class="finding-item"><span class="num">D → D</span><span class="lbl">indexing and searching <strong>sensor streams</strong></span></div>
      </div>
    </div>

    <div class="finding">
      <h3>Where support is strong — and where it is not</h3>
      <figure class="figure figure--small">
        <img src="{{ '/assets/figures/supportdimension.png' | relative_url }}" alt="Support that 30 representative prototypes provide across key analytical dimensions">
        <figcaption>
          Coverage of key dimensions across the 30 prototypes. Query-dependent ranking and discovery
          are well supported; mobility, adaptability, and Q.I ranking are not.
        </figcaption>
      </figure>
    </div>

    <div class="finding">
      <h3>Surprises in the data</h3>
      <div class="finding-grid">
        <div class="finding-item"><span class="num">~50%</span><span class="lbl">of prototypes support <strong>storage and search scalability</strong>, mostly via virtual collections and distribution</span></div>
        <div class="finding-item"><span class="num">&lt; 40%</span><span class="lbl">address <strong>mobility</strong> of physical objects</span></div>
        <div class="finding-item"><span class="num">Few</span><span class="lbl">support searching for real-world <strong>functionality</strong>, despite its importance to smart environments</span></div>
      </div>
    </div>
  </div>
</section>

<section class="section section--alt">
  <div class="container">
    <h2>Open issues toward an "ideal" WoT search engine</h2>
    <p>
      The survey closes with a research agenda around an ideal WoTSE that can find
      <em>anything</em>, at <em>anywhere</em>, and <em>anytime</em>. Six open issues stand out:
    </p>

    <div class="archetypes-grid">
      <div class="archetype">
        <div class="archetype-num">01</div>
        <h3>Crawling the WoT</h3>
        <p>Detecting WoT data sources (IoT clouds, live maps, crowdsensing, public sensing), extracting their XHR payloads, and integrating overlapping coverage automatically.</p>
      </div>

      <div class="archetype">
        <div class="archetype-num">02</div>
        <h3>Location-based search</h3>
        <p>Coordinate systems with the right granularity per scenario, plus landmarks that translate naturally into queries and results.</p>
      </div>

      <div class="archetype">
        <div class="archetype-num">03</div>
        <h3>Taming WoT's dynamicity</h3>
        <p>Indexing prediction models rather than raw readings; balancing freshness against communication overhead; supporting continuous queries.</p>
      </div>

      <div class="archetype">
        <div class="archetype-num">04</div>
        <h3>Handling diversity</h3>
        <p>Modular construction so search engines can be composed from standardised modules that match the meta-path of a query.</p>
      </div>

      <div class="archetype">
        <div class="archetype-num">05</div>
        <h3>Scaling to 50 billion devices</h3>
        <p>Pushing search engines to the edge of WoT and federating them — naturally local, but globally addressable.</p>
      </div>

      <div class="archetype">
        <div class="archetype-num">06</div>
        <h3>Security, privacy, trust</h3>
        <p>Protecting searchers, sensor owners, and sensed persons; validating discovered readings against past patterns; auditable WoTSEs.</p>
      </div>
    </div>
  </div>
</section>

<section class="section">
  <div class="container">
    <h2>Abstract</h2>
    <p>
      Technological advances allow more physical objects to connect to the Internet and provide their services on the Web as resources. Search engines are the key to fully utilize this emerging Web of Things, as they bridge users and applications with resources needed for their operation. Developing these systems is a challenging and diverse endeavor due to the diversity of Web of Things resources that they work with. Each combination of resources in query resolution process requires a different type of search engine with its own technical challenges and usage scenarios. This diversity complicates both the development of new systems and assessment of the state of the art. In this article, we present a systematic survey on Web of Things Search Engines (WoTSE), focusing on the diversity in forms of these systems. We collect and analyze over 200 related academic works to build a flexible conceptual model for WoTSE. We develop an analytical framework on this model to review the development of the field and its current status, reflected by 30 representative works in the area. We conclude our survey with a discussion on open issues to bridge the gap between the existing progress and an ideal WoTSE.
    </p>
  </div>
</section>

<section class="section section--alt">
  <div class="container">
    <h2>BibTeX</h2>
    <pre class="bibtex"><code>@article{tran2017searching,
  title={Searching the web of things: state of the art, challenges, and solutions},
  author={Tran, Nguyen Khoi and Sheng, Quan Z and Babar, Muhammad Ali and Yao, Lina},
  journal={ACM Computing Surveys (CSUR)},
  volume={50},
  number={4},
  pages={1--34},
  year={2017},
  publisher={ACM New York, NY, USA}
}</code></pre>

    <p class="doi-line">
      DOI: <a href="https://doi.org/10.1145/3092695" rel="noopener">10.1145/3092695</a>
    </p>
  </div>
</section>
