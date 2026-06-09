<!DOCTYPE html>
<html lang="zh-Hant-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>International Internship Program | IAMS-IIP</title>
    <!-- Bootstrap 5 CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
    <!-- Font Awesome Icons -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <!-- Google Fonts: Jost (字體一律使用 Jost) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Jost:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
    
    <style>
        /* 全域字體與基本色調 */
        body {
            font-family: "Jost", sans-serif;
            background-color: #fafbfc;
            color: #1e293b;
            scroll-behavior: smooth;
            position: relative;
        }

        /* 滿版 Banner 區塊 (高度為 45vh，更新背景圖網址) */
        .hero-banner {
            /* height: 45vh; */
            min-height: 380px;
            background: linear-gradient(rgba(12, 33, 62, 0.85), rgba(12, 33, 62, 0.7)), 
                        url('https://boki-iams.github.io/IAMS-IIP/banner-400.jpg') no-repeat ;
            /* background-size: cover; */
            background-attachment: fixed;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }
        .hero-banner::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 8px;
            background: linear-gradient(90deg, #002d62, #ffb310, #002d62); /* 底部漸變金屬飾條 */
        }
        .hero-title {
            font-weight: 800;
            font-size: 3.5rem;
            letter-spacing: 2px;
            color: #ffffff;
            margin-bottom: 1.2rem;
            text-transform: uppercase;
            line-height: 1.2;
        }
        .hero-subtitle {
            font-weight: 400;
            font-size: 1.5rem;
            color: #ffb310; /* 官網金色副標 */
            margin-bottom: 0;
            letter-spacing: 1.5px;
            text-transform: uppercase;
            border-bottom: 1px solid rgba(229, 168, 35, 0.4);
            display: inline-block;
            padding-bottom: 12px;
        }

        /* 區塊通用樣式 */
        .section-padding {
            padding: 110px 0;
        }
        .section-title-wrapper {
            margin-bottom: 70px;
        }
        .section-title {
            font-weight: 700;
            font-size: 2.4rem;
            color: #002d62;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            display: inline-block;
            position: relative;
            padding-bottom: 15px;
        }
        .section-title::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 3px;
            background-color: #ffb310; /* 金色底線 */
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
        }

        /* 學術簡約卡片樣式 */
        .academic-card {
            background-color: #ffffff;
            border: 1px solid rgba(0, 45, 98, 0.08);
            border-left: 5px solid #002d62; /* 藍色側條 */
            border-radius: 4px; /* 扁平直角化 */
            padding: 40px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.02);
            transition: all 0.3s ease;
            height: 100%;
        }
        .academic-card:hover {
            border-left-color: #ffb310; /* 懸停時轉為金色側條 */
            transform: translateY(-4px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.05);
        }

        /* 金色版卡片 (強調用) */
        .academic-card-accent {
            border-left: 5px solid #ffb310;
        }

        .icon-square {
            width: 60px;
            height: 60px;
            background-color: rgba(0, 45, 98, 0.05);
            border-radius: 4px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 25px;
            color: #002d62;
            font-size: 1.6rem;
            transition: all 0.3s ease;
        }
        .academic-card:hover .icon-square {
            background-color: #ffb310;
            color: #002d62;
        }

        /* 申請時序與大會議程感排版 */
        .agenda-step {
            display: flex;
            margin-bottom: 30px;
            position: relative;
        }
        .agenda-step:last-child {
            margin-bottom: 0;
        }
        .agenda-badge {
            min-width: 50px;
            height: 50px;
            background-color: #002d62;
            color: #ffb310; /* 金色數字 */
            font-weight: 700;
            font-size: 1.2rem;
            border-radius: 4px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 25px;
            border: 1px solid rgba(229, 168, 35, 0.3);
            transition: all 0.3s ease;
        }
        .academic-card:hover .agenda-badge {
            background-color: #ffb310;
            color: #002d62;
            border-color: #ffb310;
        }
        .agenda-content {
            flex-grow: 1;
        }
        .agenda-title {
            font-weight: 600;
            color: #002d62;
            margin-bottom: 6px;
            font-size: 1.1rem;
        }

        /* 聯絡資訊樣式 */
        .info-table-row {
            border-bottom: 1px dashed rgba(0, 45, 98, 0.1);
            padding: 15px 0;
            display: flex;
            align-items: center;
        }
        .info-table-row:last-child {
            border-bottom: none;
        }
        .info-label {
            font-weight: 600;
            color: #002d62;
            min-width: 100px;
            font-size: 0.95rem;
            text-transform: uppercase;
        }
        .info-value {
            color: #4a5568;
            font-size: 0.95rem;
        }
        .info-value a {
            color: #002d62;
            text-decoration: none;
            border-bottom: 1px solid rgba(0, 45, 98, 0.3);
            transition: all 0.2s;
        }
        .info-value a:hover {
            color: #ffb310;
            border-bottom-color: #ffb310;
        }

        /* 頁尾 */
        footer {
            background-color: #0c213e;
            color: rgba(255, 255, 255, 0.7);
            padding: 40px 0;
            font-size: 0.88rem;
            border-top: 4px solid #ffb310;
        }
        footer a {
            color: #ffb310;
            text-decoration: none;
        }
        footer a:hover {
            color: #ffffff;
            text-decoration: underline;
        }

        /* 響應式微調 */
        @media (max-width: 991.98px) {
            .hero-title {
                font-size: 2.5rem;
            }
            .hero-subtitle {
                font-size: 1.2rem;
            }
            .section-padding {
                padding: 70px 0;
            }
        }
        @media (max-width: 576px) {
            .hero-banner {
                height: 45vh;
                min-height: 320px;
                padding: 40px 0;
            }
            .hero-title {
                font-size: 1.8rem;
            }
            .hero-subtitle {
                font-size: 1rem;
            }
            .agenda-step {
                flex-direction: column;
            }
            .agenda-badge {
                margin-bottom: 15px;
            }
        }
    </style>
</head>
<body>

    <!-- 滿版 Banner 區塊 (高度為 45vh) -->
    <header id="home" class="hero-banner">
        <div class="container px-4 text-center">
            <div class="row justify-content-center">
                <div class="col-lg-12">
                    <h1 class="hero-title">International Internship Program</h1>
                    <p class="hero-subtitle">Institute of Atomic and Molecular Sciences (IAMS-IIP)</p>
                </div>
            </div>
        </div>
    </header>

    <!-- 計劃宗旨與對象 (統一為 col-lg-10) -->
    <section id="objective" class="section-padding bg-white">
        <div class="container">
            <div class="text-center section-title-wrapper">
                <h2 class="section-title">Program Objective</h2>
            </div>
            <div class="row justify-content-center">
                <div class="col-lg-10">
                    <div class="academic-card">
                        <div class="row align-items-center">
                            <div class="col-md-2 text-center mb-4 mb-md-0">
                                <div class="icon-square mx-auto">
                                    <i class="fa-solid fa-graduation-cap"></i>
                                </div>
                            </div>
                            <div class="col-md-10">
                                <h4 class="mb-3" style="color: #002d62; font-weight: 700; letter-spacing: 0.5px;">Target Applicants & Objective</h4>
                                <p class="fs-5 mb-0" style="line-height: 1.8; font-weight: 300; color: #4a5568;">
                                    IAMS-IIP offers an opportunity to undergraduate/ graduate students from overseas universities to do short-term research and academic exchange with the researchers at IAMS. Via this summer intern, PIs of IAMS can cultivate and arouse students’ enthusiasm in scientific research, enhancing their willingness, especially that of excellent students, to study and do research at our institute in the future. We believe that IAMS will also benefit a lot from this bilateral cooperation.
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 實習期間 (統一為 col-lg-10) -->
    <section id="period" class="section-padding" style="background-color: #f4f6f9;">
        <div class="container">
            <div class="text-center section-title-wrapper">
                <h2 class="section-title">Internship Period</h2>
            </div>
            <div class="row justify-content-center">
                <div class="col-lg-10">
                    <div class="academic-card academic-card-accent text-center">
                        <div class="icon-square mx-auto">
                            <i class="fa-solid fa-calendar-check"></i>
                        </div>
                        <h4 class="mb-3" style="color: #002d62; font-weight: 700;">Flexible Scheduling</h4>
                        <p class="fs-5 mb-4" style="line-height: 1.8; font-weight: 300; color: #4a5568;">
                            The internship period can be discussed between the hosting PI and the applicant. Generally speaking, the internship will last for <strong style="color: #002d62; font-weight: 600;">2 months</strong>.
                        </p>
                        <div class="d-inline-block px-4 py-2" style="background-color: rgba(0, 45, 98, 0.05); border-left: 3px solid #ffb310; font-weight: 500; color: #002d62;">
                            <i class="fa-solid fa-hourglass-half me-2" style="color: #ffb310;"></i>Typical Duration: 2 Months
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 申請時間與方法 (內部維持並排，最外層統一為 col-lg-10) -->
    <section id="application" class="section-padding bg-white">
        <div class="container">
            <div class="text-center section-title-wrapper">
                <h2 class="section-title">Application</h2>
            </div>
            <div class="row justify-content-center">
                <div class="col-lg-10">
                    <div class="row g-4 justify-content-center">
                        <!-- 申請時間 -->
                        <div class="col-md-6">
                            <div class="academic-card h-100">
                                <div class="icon-square">
                                    <i class="fa-solid fa-clock-rotate-left"></i>
                                </div>
                                <h4 class="mb-3" style="color: #002d62; font-weight: 700;">Application Time</h4>
                                <p class="fs-5 mb-4" style="line-height: 1.7; font-weight: 300; color: #4a5568;">
                                    Application for IAMS-IIP is open for the <strong style="color: #002d62; font-weight: 600;">whole year</strong>.
                                </p>
                                <div class="p-3" style="background-color: #fff9eb; border-left: 4px solid #ffb310; border-radius: 4px;">
                                    <div style="font-weight: 600; color: #b7791f;" class="mb-1">
                                        <i class="fa-solid fa-circle-exclamation me-2"></i>Submission Lead Time
                                    </div>
                                    <span class="small text-muted">Applicants have to submit the required documents at least <strong>2 months</strong> before the internship.</span>
                                </div>
                            </div>
                        </div>

                        <!-- 申請管道與流程 -->
                        <div class="col-md-6">
                            <div class="academic-card academic-card-accent h-100">
                                <div class="icon-square">
                                    <i class="fa-solid fa-arrow-down-short-wide"></i>
                                </div>
                                <h4 class="mb-4" style="color: #002d62; font-weight: 700;">Application Method</h4>
                                
                                <!-- 步驟 1 -->
                                <div class="agenda-step">
                                    <div class="agenda-badge">01</div>
                                    <div class="agenda-content">
                                        <h6 class="agenda-title">Hosting PI Approval</h6>
                                        <p class="small text-muted mb-0">The applicant has to get approval from the hosting PI to do the internship at the lab first.</p>
                                    </div>
                                </div>
                                
                                <!-- 步驟 2 -->
                                <div class="agenda-step">
                                    <div class="agenda-badge">02</div>
                                    <div class="agenda-content">
                                        <h6 class="agenda-title">Prepare & Send Materials</h6>
                                        <p class="small text-muted mb-0">The applicant has to send the required application materials, combined into one PDF, to Ms. Bonnie Lin at <a href="mailto:hsiuyu@gate.sinica.edu.tw" style="color:#002d62; font-weight: 600;">hsiuyu@gate.sinica.edu.tw</a>.</p>
                                    </div>
                                </div>

                                <!-- 步驟 3 -->
                                <div class="agenda-step">
                                    <div class="agenda-badge">03</div>
                                    <div class="agenda-content">
                                        <h6 class="agenda-title">Committee Review</h6>
                                        <p class="small text-muted mb-0">Ms. Lin will send the application to the Academic Committee at IAMS for review.</p>
                                    </div>
                                </div>
                                
                                <div class="mt-4 pt-3 border-top border-light text-muted small">
                                    <i class="fa-solid fa-circle-info me-2" style="color: #ffb310;"></i>Please refer to the “Guideline” to acquire other information.
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 聯絡我們 (統一為 col-lg-10) -->
    <section id="contact" class="section-padding" style="background-color: #f4f6f9;">
        <div class="container">
            <div class="text-center section-title-wrapper">
                <h2 class="section-title">Contact Us</h2>
            </div>
            <div class="row justify-content-center">
                <div class="col-lg-10">
                    <div class="academic-card">
                        <div class="row">
                            <div class="col-md-5 mb-4 mb-md-0 d-flex flex-column justify-content-center">
                                <span class="text-uppercase small fw-bold tracking-wider mb-2" style="color: #ffb310;">Inquiries</span>
                                <h4 style="color: #002d62; font-weight: 700; margin-bottom: 8px;">Ms. Bonnie Lin</h4>
                                <p class="text-muted small mb-0">Executive Assistant of IAMS-IIP</p>
                            </div>
                            <div class="col-md-7 border-start border-md-light ps-md-4">
                                <div class="info-table-row">
                                    <div class="info-label"><i class="fa-solid fa-location-dot me-2"></i>Address</div>
                                    <div class="info-value">R317, Institute of Atomic and Molecular Sciences, No. 1, Roosevelt Rd., Sec. 4, Taipei, 10617, Taiwan</div>
                                </div>
                                <div class="info-table-row">
                                    <div class="info-label"><i class="fa-solid fa-phone me-2"></i>Tel</div>
                                    <div class="info-value"><a href="tel:+886-2-23624928">+886-2-23624928</a></div>
                                </div>
                                <div class="info-table-row">
                                    <div class="info-label"><i class="fa-solid fa-envelope me-2"></i>E-mail</div>
                                    <div class="info-value"><a href="mailto:hsiuyu@gate.sinica.edu.tw">hsiuyu@gate.sinica.edu.tw</a></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 頁尾 -->
    <footer class="text-center">
        <div class="container">
            <p class="mb-2" style="font-weight: 500;">&copy; 2026 Institute of Atomic and Molecular Sciences (IAMS), Academia Sinica.</p>
            <p class="mb-0 text-white-50 small">All Rights Reserved. | Styled reference to OCPA10 Singapore | Fonts powered by Jost</p>
        </div>
    </footer>

    <!-- Bootstrap 5 Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
