<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Cv</title>
    <link
      href="https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css"
      rel="stylesheet"
    />
    <style>
      @import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&display=swap");
    * {
      padding: 0;
      margin: 0;
      border: none;
      list-style: none;
      box-sizing: border-box;
      text-decoration: none;
      outline: none;
      scroll-behavior: smooth;
      font-family: "Poppins", sans-serif;
    }

    :root {
      --background-color: #041c32;
      --secondary-color: #04293a;
      --main-color: #064663;
      --text-color: #ffffff;
    }

    html {
      font-size: 62.5%;
      overflow-x: hidden;
    }

    body {
      background-color: var(--background-color);
      color: var(--text-color);
    }

    .header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      padding: 2rem 9%;
      background-color: transparent;
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 100;
      transition: 0.3s;
    }

    .header.sticky {
      background: var(--background-color);
    }

    .logo {
      position: relative;
      font-size: 2.5rem;
      color: var(--text-color);
      font-weight: 600;
    }

    .navbar {
      position: relative;
    }

    .navbar a {
      font-size: 1.7rem;
      color: var(--text-color);
      font-weight: 500;
      margin-left: 3.5rem;
      transition: 0.3s;
    }

    .navbar a:hover,
    .navbar a.active {
      color: var(--main-color);
    }

    #menu-icon {
      position: relative;
      font-size: 3.6rem;
      color: var(--text-color);
      cursor: pointer;
      display: none;
    }

    section {
      min-height: 100vh;
      padding: 10rem 9% 2rem;
    }

    .home {
      display: flex;
      align-items: center;
      padding: 0 9%;
    }

    .home-content {
      max-width: 60rem;
    }

    .home-content h1 {
      position: relative;
      display: inline-block;
      font-size: 5.6rem;
      font-weight: 700;
      line-height: 1.3;
    }

    .home-content h1 span {
      color: var(--text-color);
    }

    .home-content .text-animate {
      position: relative;
      width: 32.8rem;
    }

    .home-content .text-animate h3 {
      font-size: 3.2rem;
      font-weight: 700;
      color: transparent;
      -webkit-text-stroke: 0.7px var(--main-color);
      background-image: linear-gradient(var(--main-color), var(--main-color));
      background-repeat: no-repeat;
      -webkit-background-clip: text;
      background-position: -33rem 0;
    }

    .home.show-animate .home-content .text-animate h3 {
      animation: homeBgText 6s linear infinite;
      animation-delay: 2s;
    }

    .home-content .text-animate h3::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 0;
      height: 100%;
      border-right: 2px solid var(--main-color);
      z-index: -1;
    }

    .home.show-animate .home-content .text-animate h3::before {
      animation: homeCursorText 6s linear infinite;
      animation-delay: 2s;
    }

    .home-content p {
      position: relative;
      font-size: 1.6rem;
      margin: 2rem 0 4rem;
    }

    .btn-box {
      position: relative;
      display: flex;
      width: 17rem;
      height: 5rem;
    }

    .btn-box .btn {
      position: relative;
      display: inline-flex;
      justify-content: center;
      align-items: center;
      width: 15rem;
      height: 100%;
      background: var(--main-color);
      border: 0.2rem solid var(--main-color);
      border-radius: 0.8rem;
      font-size: 1.8rem;
      font-weight: 600;
      letter-spacing: 0.1rem;
      color: var(--text-color);
      z-index: 1;
      overflow: hidden;
    }

    .btn-box .btn::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 0;
      height: 100%;
      background: var(--background-color);
      z-index: -1;
      transition: 0.5s;
    }

    .btn-box .btn:hover::before {
      width: 100%;
    }

    .home-sci {
      position: absolute;
      bottom: 4rem;
      width: 200px;
      display: flex;
      justify-content: space-between;
    }

    .home-sci a {
      position: relative;
      display: inline-flex;
      justify-content: center;
      align-items: center;
      width: 40px;
      height: 40px;
      background: transparent;
      border: 0.2rem solid var(--main-color);
      border-radius: 50%;
      font-size: 20px;
      color: var(--main-color);
      z-index: 1;
      overflow: hidden;
      transition: 0.5s;
    }

    .home-sci a:hover {
      color: var(--text-color);
      border: 0.2rem solid var(--text-color);
    }

    .home-sci a::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 0;
      height: 100%;
      background: var(--main-color);
      z-index: -1;
      transition: 0.5s;
    }

    .home-sci a:hover::before {
      width: 100%;
    }

    .about {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      gap: 2rem;
      background: var(--secondary-color);
      padding-bottom: 6rem;
    }

    .heading {
      position: relative;
      display: inline-block;
      font-size: 5rem;
      margin-bottom: 3rem;
      text-align: center;
    }

    span {
      color: var(--main-color);
    }

    .about-img {
      position: relative;
      width: 25rem;
      height: 25rem;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      transition: 0.5s;
    }

    .about-img img {
      width: 90%;
      height: 90%;
      border-radius: 50%;
      border: 0.2rem solid var(--main-color);
    }

    .about-img .circle-spin {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) rotate(0);
      width: 100%;
      height: 100%;
      border-radius: 50%;
      border-top: 0.2rem solid var(--secondary-color);
      border-bottom: 0.2rem solid var(--secondary-color);
      border-left: 0.2rem solid var(--main-color);
      border-right: 0.2rem solid var(--main-color);
      animation: aboutSpinner 8s linear infinite;
    }

    .about-content {
      text-align: center;
    }

    .about-content h3 {
      position: relative;
      display: inline-block;
      font-size: 2.6rem;
    }

    .about-content p {
      position: relative;
      font-size: 1.6rem;
      margin: 2rem 0 3rem;
    }

    .btn-box.btns {
      display: inline-block;
      width: 15rem;
    }

    .btn-box.btns a::before {
      background: var(--secondary-color);
    }

    .education {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      min-height: auto;
      padding-bottom: 5rem;
    }

    .education .education-row {
      display: flex;
      flex-wrap: wrap;
      gap: 5rem;
    }

    .education-row .education-column {
      flex: 1 1 40rem;
    }

    .education-column .title {
      position: relative;
      display: inline-block;
      font-size: 2.5rem;
      margin: 0 0 1.5rem 2rem;
    }

    .education-column .education-box {
      position: relative;
      border-left: 0.2rem solid var(--main-color);
    }

    .education-box .education-content {
      position: relative;
      padding-left: 2rem;
    }

    .education-box .education-content::before {
      content: "";
      position: absolute;
      top: 0;
      left: -1.1rem;
      width: 2rem;
      height: 2rem;
      background: var(--main-color);
      border-radius: 50%;
    }

    .education-content .content {
      position: relative;
      padding: 1.5rem;
      border: 0.2rem solid var(--main-color);
      border-radius: 0.6rem;
      margin-bottom: 2rem;
      overflow: hidden;
    }

    .education-content .content::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 0;
      height: 100%;
      background: var(--secondary-color);
      z-index: -1;
      transition: 0.5s;
    }

    .education-content .content:hover::before {
      width: 100%;
    }

    .education-content .content .year {
      font-size: 1.5rem;
      color: var(--main-color);
      padding-bottom: 0.5rem;
    }

    .education-content .content .year i {
      padding-right: 0.5rem;
    }

    .education-content .content h3 {
      font-size: 2rem;
    }

    .education-content .content p {
      font-size: 1.6rem;
      padding-top: 0.5rem;
    }

    .skills {
      min-height: auto;
      padding-bottom: 7rem;
      background: var(--secondary-color);
    }

    .skills h2 {
      display: inline-block;
      left: 50%;
      transform: translateX(-50%);
    }

    .skills-row {
      display: flex;
      flex-wrap: wrap;
      gap: 5rem;
    }

    .skills-row .skills-column {
      flex: 1 1 40rem;
    }

    .skills-column .title {
      position: relative;
      display: inline-block;
      font-size: 2.5rem;
      margin: 0 0 1.5rem;
    }

    .skills-column .skills-box {
      position: relative;
    }

    .skills-box .skills-content {
      position: relative;
      border: 0.2rem solid var(--main-color);
      border-radius: 0.6rem;
      padding: 0.5rem 1.5rem;
      z-index: 1;
      overflow: hidden;
    }

    .skills-box .skills-content::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 0;
      height: 100%;
      background-color: var(--background-color);
      z-index: -1;
      transition: 0.5s;
    }

    .skills-box .skills-content:hover:before {
      width: 100%;
    }

    .skills-content .progress {
      padding: 1rem 0;
    }

    .skills-content .progress h3 {
      font-size: 1.7rem;
      display: flex;
      justify-content: space-between;
    }

    .skills-content .progress h3 span {
      color: var(--text-color);
    }

    .skills-content .progress .bar {
      height: 2.5rem;
      border-radius: 0.6rem;
      border: 0.2rem solid var(--main-color);
      padding: 0.5rem;
      margin: 1rem 0;
    }

    .skills-content .progress .bar span {
      display: block;
      height: 100%;
      border-radius: 0.3rem;
      background: var(--main-color);
    }

    .skills-column:nth-child(1) .skills-content .progress:nth-child(1) .bar span {
      width: 90%;
    }
    .skills-column:nth-child(1) .skills-content .progress:nth-child(2) .bar span {
      width: 70%;
    }
    .skills-column:nth-child(1) .skills-content .progress:nth-child(3) .bar span {
      width: 40%;
    }
    .skills-column:nth-child(1) .skills-content .progress:nth-child(4) .bar span {
      width: 60%;
    }

    .skills-column:nth-child(2) .skills-content .progress:nth-child(1) .bar span {
      width: 100%;
    }
    .skills-column:nth-child(2) .skills-content .progress:nth-child(2) .bar span {
      width: 90%;
    }
    .skills-column:nth-child(2) .skills-content .progress:nth-child(3) .bar span {
      width: 80%;
    }
    .skills-column:nth-child(2) .skills-content .progress:nth-child(4) .bar span {
      width: 70%;
    }
    .skills-column:nth-child(2) .skills-content .progress:nth-child(5) .bar span {
      width: 90%;
    }

    .footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      padding: 2rem 9%;
      background: var(--background-color);
    }

    .footer-text,
    .footer-iconTop {
      position: relative;
    }

    .footer-text p {
      font-size: 1.6rem;
    }

    .footer-iconTop a {
      position: relative;
      display: inline-flex;
      justify-content: center;
      align-items: center;
      padding: 0.8rem;
      background: var(--main-color);
      border: 0.2rem solid var(--main-color);
      border-radius: 0.6rem;
      z-index: 1;
      overflow: hidden;
    }

    .footer-iconTop a::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 0;
      height: 100%;
      background: var(--secondary-color);
      z-index: -1;
      transition: 0.5s;
    }

    .footer-iconTop a:hover::before {
      width: 100%;
    }

    .footer-iconTop a i {
      font-size: 2.4rem;
      color: var(--background-color);
      transition: 0.5s;
    }

    .footer-iconTop a:hover i {
      color: var(--main-color);
    }

    .animate {
      position: absolute;
      top: 0;
      right: 0;
      width: 100%;
      height: 100%;
      background: var(--background-color);
      z-index: 98;
    }

    .logo .animate,
    .navbar .animate,
    #menu-icon .animate,
    .home.show-animate .animate {
      animation: showRight 1s ease forwards;
      animation-delay: calc(0.3s * var(--i));
    }

    .animate.scroll {
      transition: 1s ease;
      transition-delay: calc(0.3s / var(--i));
      animation: none;
    }

    section:nth-child(odd) .animate.scroll {
      background: var(--secondary-color);
    }

    .education .education-box .animate.scroll {
      width: 105%;
    }

    .about.show-animate .animate.scroll,
    .education.show-animate .animate.scroll,
    .skills.show-animate .animate.scroll,
    .footer.show-animate .animate.scroll {
      transition-delay: calc(0.3s * var(--i));
      width: 0;
    }

    @media (min-width: 1281px) {
      .about-img:hover {
        width: 40rem;
        height: 40rem;
        transition: 0.5s;
      }
    }

    @media (max-width: 1200px) {
      html {
        font-size: 55%;
      }
    }

    @media (max-width: 991px) {
      .header {
        padding: 2rem 4%;
      }

      section {
        padding: 10rem 4% 2rem;
      }

      .home {
        padding: 0 4%;
      }

      .footer {
        padding: 2rem 4%;
      }
    }

    @media (max-width: 768px) {
      .header {
        background: var(--background-color);
      }

      #menu-icon {
        display: block;
      }

      .navbar {
        position: absolute;
        top: 100%;
        left: -100%;
        width: 100%;
        padding: 1rem 4%;
        background: var(--secondary-color);
        box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.2);
        z-index: 1;
        transition: 0.25s ease;
        transition-delay: 0.25s;
      }

      .navbar.active {
        left: 0;
        transition-delay: 0s;
      }

      .navbar .active-nav {
        position: absolute;
        top: 0;
        left: -100%;
        width: 100%;
        height: 100%;
        background: var(--background-color);
        border-top: 0.1rem solid rgba(0, 0, 0, 0.2);
        z-index: -1;
        transition: 0.2s ease;
        transition-delay: 0s;
      }

      .navbar.active .active-nav {
        transition-delay: 0.2s;
        left: 0;
      }

      .navbar a {
        display: block;
        font-size: 2rem;
        margin: 3rem 0;
        transform: translateX(-20rem);
        transition: 0.25s ease;
        transition-delay: 0s;
      }

      .navbar.active a {
        transform: translateX(0);
        transition-delay: 0.25s;
      }
    }

    @media (max-width: 520px) {
      html {
        font-size: 50%;
      }

      .home-content h1 {
        display: flex;
        flex-direction: column;
      }

      .home-sci {
        width: 160px;
      }

      .home-sci a {
        width: 34px;
        height: 34px;
      }
    }

    @media (max-width: 462px) {
      .home-content h1 {
        font-size: 5.2rem;
      }

      .education {
        padding: 10rem 4% 5rem 5%;
      }

      .home-content p,
      .about-content p,
      .education-row,
      .skills-row,
      .btn-box {
        padding-right: 2rem;
      }

      .footer {
        padding-right: 5rem;
      }
    }

    @media (max-width: 371px) {
      .home {
        justify-content: center;
        text-align: center;
      }

      .about-content {
        display: flex;
        align-items: center;
        flex-direction: column;
        text-align: center;
      }

      .home-content h1 {
        font-size: 5rem;
      }

      .home-content h3 {
        position: relative;
        display: flex;
        margin: auto;
      }

      .home-content .text-animate {
        position: relative;
        display: flex;
        width: 36rem;
        margin: auto;
      }

      .home-content p,
      .about-content p {
        text-align: center;
      }

      .btn-box {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: auto;
      }

      .home-content p,
      .about-content p,
      .education-row,
      .skills-row,
      .btn-box {
        padding-right: 2rem;
      }

      .footer {
        padding-right: 4rem;
      }
    }

    @keyframes homeBgText {
      0%,
      10%,
      100% {
        background-position: -33rem 0;
      }

      65%,
      85% {
        background-position: 0 0;
      }
    }

    @keyframes homeCursorText {
      0%,
      10%,
      100% {
        width: 0;
      }

      65%,
      78%,
      85% {
        width: 100%;
        opacity: 1;
      }

      75%,
      81% {
        opacity: 0;
      }
    }

    @keyframes aboutSpinner {
      100% {
        transform: translate(-50%, -50%) rotate(360deg);
      }
    }

    @keyframes showRight {
      100% {
        width: 0;
      }
    }

    </style>
  </head>
  <body>
    <header class="header">
      <a href="#home" class="logo"
        >Iwan.<span class="animate" style="--i: 1"></span>
      </a>

      <div class="bx bx-menu" id="menu-icon">
        <span class="animate" style="--i: 2"></span>
      </div>

      <nav class="navbar">
        <a href="#home" class="active">Home</a>
        <a href="#about">About</a>
        <a href="#education">Resume</a>
        <a href="#skills">Skills</a>

        <span class="active-nav"></span>
        <span class="animate" style="--i: 2"></span>
      </nav>
    </header>

    <section class="home show-animate" id="home">
      <div class="home-content">
        <h1>
          Hi, I'm <span>Iwan Sanusi.</span
          ><span class="animate" style="--i: 2"></span>
        </h1>
        <div class="text-animate">
          <h3>Mahasiswa STMIK</h3>
          <span class="animate" style="--i: 3"></span>
        </div>

        <p>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Soluta at
          quaerat, consectetur eius aliquid excepturi ab aspernatur consequatur
          iure repudiandae repellendus sit odit ducimus. Nemo voluptatum nulla
          tenetur asperiores alias.
          <span class="animate" style="--i: 4"></span>
        </p>

        <div class="btn-box">
          <a href="#" class="btn">Follow me</a>
          <span class="animate" style="--i: 5"></span>
        </div>
      </div>

      <div class="home-sci">
        <a href="https://www.instagram.com/_yxwannn/" target="_blank"
          ><i class="bx bxl-instagram"></i
        ></a>
        <a href="https://t.me/helloword1111" target="_blank"
          ><i class="bx bxl-telegram"></i
        ></a>
        <a href="https://github.com/h3h3y" target="_blank"
          ><i class="bx bxl-github"></i
        ></a>
        <a href="https://youtube.com/@krenzengaming3661" target="_blank"
          ><i class="bx bxl-youtube"></i
        ></a>
        <span class="animate" style="--i: 6"></span>
      </div>
    </section>

    <section class="about" id="about">
      <h2 class="heading">
        About <span>Me</span><span class="animate scroll" style="--i: 1"></span>
      </h2>

      <div class="about-img">
        <img src="img/iwan.jpg" alt="about" />
        <span class="circle-spin"></span>
        <span class="animate scroll" style="--i: 2"></span>
      </div>

      <div class="about-content">
        <h3>
          Mahasiswa STMIK<span class="animate scroll" style="--i: 3"></span>
        </h3>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequatur
          suscipit consectetur ducimus neque odit repudiandae aliquid aliquam,
          deserunt dicta sint possimus? Harum, quibusdam iure possimus, est,
          officiis ea rem tempore iusto velit earum perferendis vel pariatur
          mollitia atque nam veniam repellendus exercitationem asperiores
          aspernatur? Sunt sint maiores impedit ex animi.
          <span class="animate scroll" style="--i: 4"></span>
        </p>

        <div class="btn-box btns">
          <a href="#more" class="btn">Read More</a>
          <span class="animate scroll" style="--i: 5"></span>
        </div>
      </div>
    </section>

    <section class="education" id="education">
      <h2 class="heading">
        My <span>Resume</span
        ><span class="animate scroll" style="--i: 1"></span>
      </h2>

      <div class="education-row" id="more">
        <div class="education-column">
          <h3 class="title">
            Education<span class="animate scroll" style="--i: 2"></span>
          </h3>

          <div class="education-box">
            <div class="education-content">
              <div class="content">
                <div class="year">
                  <i class="bx bxs-calendar-alt"></i> 2010 - 2016
                </div>
                <h3>SD N 1 Sidosari</h3>
                <p>
                  Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                  Reiciendis nisi ipsam quibusdam, tempora vel, ea qui beatae
                  amet omnis dolor possimus rem, iste nihil dolore quo sed.
                  Nesciunt, explicabo amet?
                </p>
              </div>
            </div>

            <div class="education-content">
              <div class="content">
                <div class="year">
                  <i class="bx bxs-calendar-alt"></i> 2016 - 2019
                </div>
                <h3>SMP N 1 Kesesi</h3>
                <p>
                  Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                  Reiciendis nisi ipsam quibusdam, tempora vel, ea qui beatae
                  amet omnis dolor possimus rem, iste nihil dolore quo sed.
                  Nesciunt, explicabo amet?
                </p>
              </div>
            </div>

            <div class="education-content">
              <div class="content">
                <div class="year">
                  <i class="bx bxs-calendar-alt"></i> 2019 - 2022
                </div>
                <h3>SMK Muhammadiyah Kesesi</h3>
                <p>
                  Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                  Reiciendis nisi ipsam quibusdam, tempora vel, ea qui beatae
                  amet omnis dolor possimus rem, iste nihil dolore quo sed.
                  Nesciunt, explicabo amet?
                </p>
              </div>
            </div>

            <div class="education-content">
              <div class="content">
                <div class="year">
                  <i class="bx bxs-calendar-alt"></i> 2022 - Sekarang
                </div>
                <h3>STMIK Pekalongan</h3>
                <p>
                  Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                  Reiciendis nisi ipsam quibusdam, tempora vel, ea qui beatae
                  amet omnis dolor possimus rem, iste nihil dolore quo sed.
                  Nesciunt, explicabo amet?
                </p>
              </div>
            </div>
            <span class="animate scroll" style="--i: 3"></span>
          </div>
        </div>

        <div class="education-column">
          <h3 class="title">
            Experience<span class="animate scroll" style="--i: 5"></span>
          </h3>

          <div class="education-box">
            <div class="education-content">
              <div class="content">
                <div class="year">
                  <i class="bx bxs-calendar-alt"></i> 3 Months
                </div>
                <h3>Training Bootcamp Html,CSS,Java Script</h3>
                <p>
                  Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                  Reiciendis nisi ipsam quibusdam, tempora vel, ea qui beatae
                  amet omnis dolor possimus rem, iste nihil dolore quo sed.
                  Nesciunt, explicabo amet?
                </p>
              </div>
            </div>

            <div class="education-content">
              <div class="content">
                <div class="year">
                  <i class="bx bxs-calendar-alt"></i> 3 Months
                </div>
                <h3>PKL Hardware & Printer Solution</h3>
                <p>
                  Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                  Reiciendis nisi ipsam quibusdam, tempora vel, ea qui beatae
                  amet omnis dolor possimus rem, iste nihil dolore quo sed.
                  Nesciunt, explicabo amet?
                </p>
              </div>
            </div>

            <div class="education-content">
              <div class="content">
                <div class="year"><i class="bx bxs-calendar-alt"></i> 2020</div>
                <h3>Participant Nasional Web Design (HIEDESCOM)</h3>
                <p>
                  Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                  Reiciendis nisi ipsam quibusdam, tempora vel, ea qui beatae
                  amet omnis dolor possimus rem, iste nihil dolore quo sed.
                  Nesciunt, explicabo amet?
                </p>
              </div>
            </div>

            <div class="education-content">
              <div class="content">
                <div class="year"><i class="bx bxs-calendar-alt"></i> 2022</div>
                <h3>Participant Competition FrontEnd & Backend Web Design</h3>
                <p>
                  Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                  Reiciendis nisi ipsam quibusdam, tempora vel, ea qui beatae
                  amet omnis dolor possimus rem, iste nihil dolore quo sed.
                  Nesciunt, explicabo amet?
                </p>
              </div>
            </div>
            <span class="animate scroll" style="--i: 6"></span>
          </div>
        </div>
      </div>
    </section>

    <section class="skills" id="skills">
      <h2 class="heading">
        My <span>Skills</span
        ><span class="animate scroll" style="--i: 1"></span>
      </h2>

      <div class="skills-row">
        <div class="skills-column">
          <h3 class="title">
            Coding Skills<span class="animate scroll" style="--i: 2"></span>
          </h3>

          <div class="skills-box">
            <div class="skills-content">
              <div class="progress">
                <h3>HTML <span>90%</span></h3>
                <div class="bar"><span></span></div>
              </div>

              <div class="progress">
                <h3>CSS <span>70%</span></h3>
                <div class="bar"><span></span></div>
              </div>

              <div class="progress">
                <h3>Java Script <span>40%</span></h3>
                <div class="bar"><span></span></div>
              </div>

              <div class="progress">
                <h3>PHP <span>60%</span></h3>
                <div class="bar"><span></span></div>
              </div>
            </div>
            <span class="animate scroll" style="--i: 3"></span>
          </div>
        </div>

        <div class="skills-column">
          <h3 class="title">
            Excess<span class="animate scroll" style="--i: 5"></span>
          </h3>

          <div class="skills-box">
            <div class="skills-content">
              <div class="progress">
                <h3>Honesty <span>100%</span></h3>
                <div class="bar"><span></span></div>
              </div>

              <div class="progress">
                <h3>Hard Woker <span>90%</span></h3>
                <div class="bar"><span></span></div>
              </div>

              <div class="progress">
                <h3>Flexible <span>80%</span></h3>
                <div class="bar"><span></span></div>
              </div>

              <div class="progress">
                <h3>Communication <span>70%</span></h3>
                <div class="bar"><span></span></div>
              </div>

              <div class="progress">
                <h3>Discipline <span>90%</span></h3>
                <div class="bar"><span></span></div>
              </div>
            </div>
            <span class="animate scroll" style="--i: 6"></span>
          </div>
        </div>
      </div>
    </section>

    <footer class="footer">
      <div class="footer-text">
        <p>&copy; 2023 | My Portofolio</p>
        <span class="animate scroll" style="--i: 1"></span>
      </div>

      <div class="footer-iconTop">
        <a href="#home"><i class="bx bxs-to-top"></i></a>
        <span class="animate scroll" style="--i: 3"></span>
      </div>
    </footer>

    <!-- Java Script -->
    <script>
      let menuIcon = document.querySelector("#menu-icon");
      let navbar = document.querySelector(".navbar");

      menuIcon.onclick = () => {
        menuIcon.classList.toggle("bx-x");
        navbar.classList.toggle("active");
      };

      let sections = document.querySelectorAll("section");
      let navLinks = document.querySelectorAll("header nav a");
      window.onscroll = () => {
        sections.forEach((sec) => {
          let top = window.scrollY;
          let offset = sec.offsetTop - 100;
          let height = sec.offsetHeight;
          let id = sec.getAttribute("id");

          if (top >= offset && top < offset + height) {
            navLinks.forEach((links) => {
              links.classList.remove("active");
              document
                .querySelector("header nav a[href*=" + id + "]")
                .classList.add("active");
            });
            sec.classList.add("show-animate");
          } else {
            sec.classList.remove("show-animate");
          }
        });

        let header = document.querySelector("header");
        header.classList.toggle("sticky", window.scrollY > 100);

        menuIcon.classList.remove("bx-x");
        navbar.classList.remove("active");

        let footer = document.querySelector("footer");
        footer.classList.toggle(
          "show-animate",
          this.innerHeight + this.scrollY >=
            document.scrollingElement.scrollHeight
        );
      };
    </script>
  </body>
</html>
