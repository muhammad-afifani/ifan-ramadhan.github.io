<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Muhammad Afifani Romadhan - CV</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/ScrollTrigger.min.js"></script>
    <style>
        :root {
            --primary: #2a4365;
            --secondary: #3182ce;
            --accent: #63b3ed;
            --light: #f7fafc;
            --dark: #1a202c;
            --gray: #718096;
            --success: #48bb78;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--light);
            color: var(--dark);
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1rem;
        }

        section {
            padding: 4rem 0;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 2rem 0;
            position: relative;
            overflow: hidden;
        }

        .header-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0.1;
            background: repeating-linear-gradient(
                45deg,
                transparent,
                transparent 20px,
                rgba(255, 255, 255, 0.1) 20px,
                rgba(255, 255, 255, 0.1) 40px
            );
        }

        .profile {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            position: relative;
        }

        .profile-photo {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background: var(--accent);
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
            font-size: 4rem;
            color: white;
            text-transform: uppercase;
            margin-bottom: 2rem;
            cursor: pointer;
            transition: transform 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .profile-photo:hover {
            transform: scale(1.05);
        }

        .profile-photo:after {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(
                to bottom right,
                rgba(255, 255, 255, 0.3),
                rgba(255, 255, 255, 0)
            );
            transform: rotate(30deg);
            transition: transform 0.5s ease;
        }

        .profile-photo:hover:after {
            transform: rotate(30deg) translate(20%, 20%);
        }

        .profile-info {
            flex: 1;
            padding-left: 2rem;
        }

        .name {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            position: relative;
            display: inline-block;
        }

        .name:after {
            content: "";
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 3px;
            background: var(--accent);
            transition: width 0.5s ease;
        }

        .name:hover:after {
            width: 100%;
        }

        .contact-info {
            display: flex;
            flex-wrap: wrap;
            margin-top: 1.5rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-right: 1.5rem;
            margin-bottom: 0.5rem;
        }

        .contact-item i {
            margin-right: 0.5rem;
            color: var(--accent);
        }

        .contact-item a {
            color: white;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .contact-item a:hover {
            color: var(--accent);
        }

        .summary {
            margin-top: 1rem;
            line-height: 1.6;
            max-width: 800px;
        }

        /* Navigation */
        nav {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .nav-container {
            display: flex;
            justify-content: center;
        }

        .nav-link {
            padding: 1rem 1.5rem;
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            position: relative;
            transition: color 0.3s ease;
        }

        .nav-link:hover {
            color: var(--secondary);
        }

        .nav-link:after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 0;
            height: 3px;
            background: var(--secondary);
            transition: width 0.3s ease;
        }

        .nav-link:hover:after {
            width: 80%;
        }

        /* Experience Timeline */
        .timeline {
            position: relative;
            max-width: 1200px;
            margin: 2rem auto;
        }

        .timeline:before {
            content: "";
            position: absolute;
            top: 0;
            left: 50%;
            width: 4px;
            height: 100%;
            background: var(--gray);
            transform: translateX(-50%);
        }

        .timeline-item {
            padding: 1rem 0;
            position: relative;
            width: 50%;
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.4s ease;
        }

        .timeline-item:nth-child(odd) {
            left: 0;
            padding-right: 2rem;
        }

        .timeline-item:nth-child(even) {
            left: 50%;
            padding-left: 2rem;
        }

        .timeline-item:before {
            content: "";
            position: absolute;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background: var(--accent);
            top: 1.5rem;
        }

        .timeline-item:nth-child(odd):before {
            right: -10px;
        }

        .timeline-item:nth-child(even):before {
            left: -10px;
        }

        .timeline-card {
            background: white;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            padding: 1.5rem;
            position: relative;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .timeline-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        .timeline-card:before {
            content: "";
            position: absolute;
            width: 15px;
            height: 15px;
            background: white;
            transform: rotate(45deg);
            top: 1.5rem;
        }

        .timeline-item:nth-child(odd) .timeline-card:before {
            right: -7px;
        }

        .timeline-item:nth-child(even) .timeline-card:before {
            left: -7px;
        }

        .timeline-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 1rem;
        }

        .company {
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--primary);
            margin-bottom: 0.3rem;
            display: block;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .company:hover {
            color: var(--secondary);
        }

        .date {
            font-size: 0.9rem;
            color: var(--gray);
            background: var(--light);
            padding: 0.2rem 0.5rem;
            border-radius: 4px;
            white-space: nowrap;
        }

        .position {
            color: var(--secondary);
            font-weight: 500;
            margin-bottom: 1rem;
        }

        .responsibilities {
            margin: 0;
            padding-left: 1.2rem;
        }

        .responsibilities li {
            margin-bottom: 0.5rem;
            line-height: 1.5;
        }

        /* Education Section */
        .education-card {
            background: white;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            transform: translateY(30px);
            opacity: 0;
            transition: all 0.4s ease;
        }

        .education-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
        }

        .university {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--primary);
        }

        .degree {
            color: var(--secondary);
            margin-bottom: 0.5rem;
        }

        .gpa {
            background: var(--success);
            color: white;
            padding: 0.2rem 0.5rem;
            border-radius: 4px;
            display: inline-block;
            margin-bottom: 0.5rem;
        }

        .activities {
            margin-top: 1rem;
        }

        .activities h4 {
            margin-bottom: 0.5rem;
            color: var(--dark);
        }

        /* Skills Section */
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            margin-top: 1.5rem;
        }

        .skills-group {
            flex: 1;
            min-width: 300px;
        }

        .skills-group h3 {
            margin-bottom: 1rem;
            color: var(--primary);
            border-bottom: 2px solid var(--accent);
            padding-bottom: 0.5rem;
        }

        .skill-item {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
        }

        .skill-icon {
            width: 40px;
            height: 40px;
            background: var(--light);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 1rem;
            color: var(--primary);
            box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
        }

        .skill-detail {
            flex: 1;
        }

        .skill-name {
            font-weight: 500;
            margin-bottom: 0.2rem;
        }

        .skill-progress {
            width: 100%;
            height: 8px;
            background: #e2e8f0;
            border-radius: 4px;
            overflow: hidden;
        }

        .skill-progress-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--secondary), var(--accent));
            border-radius: 4px;
            transition: width 1s ease;
        }

        /* Training Section */
        .training-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .training-item {
            background: white;
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
            transform: translateY(30px);
            opacity: 0;
        }

        .training-item:hover {
            transform: translateY(-5px) !important;
        }

        .training-date {
            color: var(--gray);
            font-size: 0.9rem;
            display: block;
            margin-top: 0.5rem;
        }

        /* Footer */
        footer {
            background: var(--primary);
            color: white;
            padding: 2rem 0;
            text-align: center;
        }

        .footer-content {
            max-width: 600px;
            margin: 0 auto;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            margin: 1rem 0;
        }

        .footer-link {
            color: white;
            margin: 0 1rem;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-link:hover {
            color: var(--accent);
        }

        .copyright {
            color: var(--gray);
            font-size: 0.9rem;
            margin-top: 1rem;
        }

        /* Animations */
        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
            100% {
                transform: scale(1);
            }
        }

        .pulse {
            animation: pulse 2s infinite;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .profile {
                flex-direction: column;
                text-align: center;
            }

            .profile-photo {
                margin: 0 auto 2rem;
            }

            .profile-info {
                padding-left: 0;
            }

            .contact-info {
                justify-content: center;
            }

            .timeline:before {
                left: 30px;
            }

            .timeline-item {
                width: 100%;
                padding-left: 60px;
                padding-right: 0;
            }

            .timeline-item:nth-child(odd), 
            .timeline-item:nth-child(even) {
                left: 0;
            }

            .timeline-item:nth-child(odd):before, 
            .timeline-item:nth-child(even):before {
                left: 20px;
            }

            .timeline-item:nth-child(odd) .timeline-card:before, 
            .timeline-item:nth-child(even) .timeline-card:before {
                left: -7px;
            }

            .timeline-header {
                flex-direction: column;
            }

            .date {
                margin-top: 0.5rem;
            }

            .nav-container {
                flex-wrap: wrap;
            }
        }

        /* Tooltip Styles */
        .tooltip {
            position: absolute;
            background: var(--dark);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            font-size: 0.9rem;
            z-index: 100;
            opacity: 0;
            transition: opacity 0.3s ease;
            pointer-events: none;
        }

        .tooltip:after {
            content: "";
            position: absolute;
            width: 10px;
            height: 10px;
            background: var(--dark);
            transform: rotate(45deg);
        }

        .tooltip.top:after {
            bottom: -5px;
            left: 50%;
            transform: translateX(-50%) rotate(45deg);
        }

        .tooltip.bottom:after {
            top: -5px;
            left: 50%;
            transform: translateX(-50%) rotate(45deg);
        }

        /* Floating dots background animation */
        .dots-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -1;
            pointer-events: none;
        }

        .dot {
            position: absolute;
            border-radius: 50%;
            background: var(--accent);
            opacity: 0.1;
        }
    /* Fix untuk elemen yang tidak terlihat */
.timeline-item, .education-card, .training-item {
    opacity: 1 !important;
    transform: none !important;
    visibility: visible !important;
}
</style>
</head>
<body>
    <!-- Background Animation -->
    <div class="dots-bg" id="dots-bg"></div>

    <!-- Header Section -->
    <header id="home">
        <div class="header-bg"></div>
        <div class="container">
            <div class="profile">
                <div class="profile-photo" id="profile-photo">
                    <span>MAR</span>
                </div>
                <div class="profile-info">
                    <h1 class="name">Muhammad Afifani Romadhan</h1>
                    <div class="contact-info">
                        <div class="contact-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>Gresik, East Java, Indonesia</span>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-phone"></i>
                            <a href="tel:+6285259707649">+6285259707649</a>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-envelope"></i>
                            <a href="mailto:muhammad.afifani007@gmail.com">muhammad.afifani007@gmail.com</a>
                        </div>
                        <div class="contact-item">
                            <i class="fab fa-linkedin"></i>
                            <a href="https://www.linkedin.com/in/muhammad-afifani-romadhan/" target="_blank">LinkedIn Profile</a>
                        </div>
                    </div>
                    <p class="summary">
                        I am an Experienced Mechanical Engineer with over 2 years of expertise in data management,
                        energy monitoring, and reporting. Currently, I work at Pertamina Hulu Mahakam, an offshore oil
                        and gas company, where I specialize in monitoring and reporting energy and emissions data across
                        site processing areas. My work is characterized by exceptional attention to detail and the ability 
                        to deliver results quickly and accurately under tight deadlines.
                    </p>
                </div>
            </div>
        </div>
    </header>

    <!-- Navigation -->
    <nav>
        <div class="container">
            <div class="nav-container">
                <a href="#home" class="nav-link">Home</a>
                <a href="#experience" class="nav-link">Experience</a>
                <a href="#freelance" class="nav-link">Freelance</a>
                <a href="#education" class="nav-link">Education</a>
                <a href="#training" class="nav-link">Training</a>
                <a href="#skills" class="nav-link">Skills</a>
            </div>
        </div>
    </nav>

    <!-- Professional Experience Section -->
    <section id="experience">
        <div class="container">
            <h2>Professional Experience</h2>
            <div class="timeline">
                <!-- Experience 1 -->
                <div class="timeline-item">
                    <div class="timeline-card">
                        <div class="timeline-header">
                            <div>
                                <a href="https://phi.pertamina.com/" target="_blank" class="company">PT Pertamina Hulu Mahakam (PHM)</a>
                                <div class="location">Balikpapan Base Office, East Kalimantan</div>
                            </div>
                            <span class="date">May 2024 – Present</span>
                        </div>
                        <h3 class="position">Data Engineer – Energy and Emission | Sustainability (Contract)</h3>
                        <h4>Energy and Emission Calculations</h4>
                        <ul class="responsibilities">
                            <li>Collect data from each designated PIC related to emission sources and energy consumption at PHM.</li>
                            <li>Calculate emissions generated from all Combustion Engine activities (Marine Fleet, Land Transport, Copper), covering both liquid fuels (BBM) and gas fuels.</li>
                            <li>Perform emission calculations from waste gas combustion generated by flaring activities across all PHM fields.</li>
                            <li>Calculate emissions from Process and Venting activities, including Dehydrators, Storage Tanks, and fuel loading/unloading operations.</li>
                            <li>Calculate emissions from Fugitive Sources, such as pipeline, the number of engines, active wells, drilling activity, etc.</li>
                            <li>Calculate Scope 2 emissions from electricity consumption (e.g., PLN power usage).</li>
                            <li>Review updates in the API Compendium, IPCC guidelines, or other emission-related standards.</li>
                            <li>Monitor and review version updates of Pertamina's Emission Calculation tools.</li>
                        </ul>
                        <h4>Reporting</h4>
                        <ul class="responsibilities">
                            <li>Provide monthly updates to SKK MIGAS regarding environmental aspects, including production, emissions, water, and waste disposal.</li>
                            <li>Submit monthly reports to SHU on emission realization with a detailed breakdown of parameters.</li>
                            <li>Prepare and update semester reports to the Ministry of Energy and Mineral Resources (ESDM) for flaring activities.</li>
                            <li>Coordinate with all ENV Site teams for reporting in EVEREST related to LKL and LPL, including reviewing and validating data inputs.</li>
                        </ul>
                        <h4>Support</h4>
                        <ul class="responsibilities">
                            <li>Provide support for Energy Audits, including data provision, report review, and ENMS tools.</li>
                            <li>Assist with Sistem Manajemen Energi (SME) tasks, Life Cycle Assessment (LCA) studies, and other sustainability aspects.</li>
                            <li>Support events related to decarbonization, the Subroto Award, and other initiatives focusing on energy and emission aspects at PHM.</li>
                            <li>Assist ENV Engineers in activities related to ESG (Environmental, Social, and Governance) and KPI monitoring.</li>
                        </ul>
                    </div>
                </div>
                
                <!-- Experience 2 -->
                <div class="timeline-item">
                    <div class="timeline-card">
                        <div class="timeline-header">
                            <div>
                                <a href="https://www.wika.co.id/" target="_blank" class="company">PT Wijaya Karya (Persero) Tbk. (EPCC Division)</a>
                                <div class="location">Manyar Smelter Project</div>
                            </div>
                            <span class="date">Jan 2023 – May 2024</span>
                        </div>
                        <h3 class="position">Project Control Staff (Pipe Welding & Inspection Control System Coordinator) (Contract)</h3>
                        <ul class="responsibilities">
                            <li>Monitoring, controlling, and reporting progress of piping & fabrication, inspection, erection and preparing for test package.</li>
                            <li>Controlling red-line mark-up, Site Instruction for piping isometric, prepare data line list for test package, Pre-Comm, Commissioning, and monitoring pipe spool fabrication and installation.</li>
                            <li>Data analytics and project management including scheduling, progress tracing & monitoring. Familiar with Code and Standard.</li>
                            <li>Using PIC (Pipe Welding and Inspection Control), PST (Pipe Support Control Tool), and RFID-JOVIX (Pipe Tracking System) to monitor piping progress and inspection with volume more than 200,000 Dia-Inch, 17,000 Spool, 346,000 Inch-M, 6 Material Types.</li>
                            <li>Monitoring Fabrication and Installation Pipe Support with volume more than 400 Ton, 109 STD support, 3,900 support number, 30,000 total quantity.</li>
                            <li>Supporting Field Engineer to monitoring red-line mark-up ISO and align field design change.</li>
                            <li>Responsible for making schedules and overseeing weekly meetings with various divisions and piping subcontractors.</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Freelance Projects Section -->
    <section id="freelance">
        <div class="container">
            <h2>Freelance Project Experience</h2>
            <div class="timeline">
                <!-- Freelance 1 -->
                <div class="timeline-item">
                    <div class="timeline-card">
                        <div class="timeline-header">
                            <div>
                                <a href="https://www.petronas.com/" target="_blank" class="company">Petronas Carigali North Madura II Ltd.</a>
                                <div class="project">FEED Hidayah Development Project</div>
                            </div>
                            <span class="date">Jan 2025</span>
                        </div>
                        <h3 class="position">Mechanical Static Engineer (Freelance)</h3>
                        <ul class="responsibilities">
                            <li>Performing Mechanical Calculation for the Degasser & Electrostatic Coalescer skid packages as part of the Crude Oil Stabilization Unit for the Hidayah Development Project.</li>
                        </ul>
                    </div>
                </div>
                
                <!-- Freelance 2 -->
                <div class="timeline-item">
                    <div class="timeline-card">
                        <div class="timeline-header">
                            <div>
                                <a href="https://www.tripatra.com/" target="_blank" class="company">PT Tripatra Engineers and Construction</a>
                                <div class="project">FEED Bio Refinery Project</div>
                            </div>
                            <span class="date">Oct 2024</span>
                        </div>
                        <h3 class="position">Mechanical Static Engineer (Freelance)</h3>
                        <ul class="responsibilities">
                            <li>Performing Mechanical Calculation of Pressure Vessel for Iron Sponge Absorber (100-V-116 A/B) according to ASME and validation to ensure compliance with project requirements.</li>
                        </ul>
                    </div>
                </div>
                
                <!-- Freelance 3 -->
                <div class="timeline-item">
                    <div class="timeline-card">
                        <div class="timeline-header">
                            <div>
                                <a href="https://www.amman.co.id/id/amman-nusantara-gas" target="_blank" class="company">PT Amman Nusantara Gas</a>
                                <div class="project">Sumbawa LNG Terminal & Regas Facility Project</div>
                            </div>
                            <span class="date">April 2024</span>
                        </div>
                        <h3 class="position">Mechanical Engineer (FEM) (Freelance)</h3>
                        <ul class="responsibilities">
                            <li>Performing Finite Element Method (FEM) analysis on a pressure vessel to determine stress and displacement on the shell and each nozzle, knuckle head and each nozzle, as well as calculate cycle life analysis.</li>
                        </ul>
                    </div>
                </div>
                
                <!-- Freelance 4 -->
                <div class="timeline-item">
                    <div class="timeline-card">
                        <div class="timeline-header">
                            <div>
                                <a href="https://phe.pertamina.com/" target="_blank" class="company">PT Pertamina Hulu Energi</a>
                                <div class="project">Upgrading Facility SP AKBG-STAGE 1</div>
                            </div>
                            <span class="date">Feb 2024</span>
                        </div>
                        <h3 class="position">Process Engineer Estimator (Freelance)</h3>
                        <ul class="responsibilities">
                            <li>Conducting equipment sizing and process planning for heat exchanger, including shell and tube as well as plate and frame types, for tender project requirements.</li>
                        </ul>
                    </div>
                </div>
                
                <!-- Freelance 5 -->
                <div class="timeline-item">
                    <div class="timeline-card">
                        <div class="timeline-header">
                            <div>
                                <a href="https://www.antam.com/" target="_blank" class="company">PT Aneka Tambang Tbk. (2X30 MW CFPP)</a>
                                <div class="location">Pomalaa, Southeast Sulawesi</div>
                            </div>
                            <span class="date">Aug – Dec 2023</span>
                        </div>
                        <h3 class="position">Mechanical Engineer (CFD) (Freelance)</h3>
                        <ul class="responsibilities">
                            <li>Performing Computational Fluid Dynamics (CFD) simulations based on process design data and actual conditions to evaluate heat transfer processes and forces within the Heat Exchanger. Connecting this with Finite Element Analysis (FEA) Stress.</li>
                        </ul>
                    </div>
                </div>
                
                <!-- Freelance 6 -->
                <div class="timeline-item">
                    <div class="timeline-card">
                        <div class="timeline-header">
                            <div>
                                <a href="https://www.medcoenergi.com/" target="_blank" class="company">PT Medco Energi Internasional Tbk.</a>
                                <div class="project">Forel FPSO Time Charter</div>
                            </div>
                            <span class="date">Nov – Dec 2022</span>
                        </div>
                        <h3 class="position">Mechanical Engineer (CFD) (Freelance)</h3>
                        <ul class="responsibilities">
                            <li>Performing Computational Fluid Dynamics (CFD) of hydrodynamic forces above the FPSO, extending to the liquid level within the LP and HP KO Drum Flare, to assess the variation in liquid level within the acceptable range of the liquid level sensor tolerance.</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Education Section -->
    <section id="education">
        <div class="container">
            <h2>Education</h2>
            <div class="education-card">
                <div class="education-header">
                    <div>
                        <h3 class="university">UNIVERSITAS NEGERI SURABAYA</h3>
                        <div class="location">Surabaya, Indonesia</div>
                    </div>
                    <span class="date">2018 – 2022</span>
                </div>
                <div class="degree">Bachelor of Mechanical Engineering</div>
                <span class="gpa">GPA: 3.61/4.0</span>
                <div>Concentration of Skills: Energy</div>
                <p><strong>Final Project Topic:</strong> Studi Eksperimental Pengaruh Sudut Kemiringan Semi-Circular Perforated Baffle dengan Semi-Circular Fins Pada Sisi Annulus Terhadap Performa Double Pipe Heat Exchanger.</p>
                
                <div class="activities">
                    <h4>Activities & Achievements</h4>
                    <ul>
                        <li>2022 – Research Assistant of Heat and Mass Transfer Laboratory.</li>
                        <li>2021 – Team Leader of KKN Kab. Gresik 27.</li>
                        <li>2020 – Finalist of PKM 33rd National Student Creativity Competition.</li>
                        <li>2020 – Team Leader of DC (Design Community).</li>
                        <li>2019 – Chief of Engineering Design at DC.</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Training Section -->
    <section id="training">
        <div class="container">
            <h2>Training Experience</h2>
            <div class="training-list">
                <div class="training-item">
                    <h3>Mastering Crude Oil Distillation</h3>
                    <p>The Key to Oil and Gas Process Engineering Expertise</p>
                    <span class="training-date">March 2024</span>
                </div>
                
                <div class="training-item">
                    <h3>Piping Stress Analysis using CAESAR II</h3>
                    <span class="training-date">May 2023</span>
                </div>
                
                <div class="training-item">
                    <h3>Static Equipment Design using PV Elite</h3>
                    <span class="training-date">July 2023</span>
                </div>
                
                <div class="training-item">
                    <h3>Interpretation Drawing P&ID, Isometric, Layout, Rotating and Static Equipment</h3>
                    <span class="training-date">February 2023</span>
                </div>
                
                <div class="training-item">
                    <h3>Process Simulation for Basic</h3>
                    <p>Hands-on Simulator Software with Study Case</p>
                    <span class="training-date">October – November 2022</span>
                </div>
                
                <div class="training-item">
                    <h3>PDMS Piping Mechanical Oil & Gas Design Course</h3>
                    <span class="training-date">October 2022</span>
                </div>
                
                <div class="training-item">
                    <h3>Agile Innovation Project-Based Learning</h3>
                    <span class="training-date">August 2021 – February 2022</span>
                </div>
                
                <div class="training-item">
                    <h3>Basic Piping and Instrument Diagram with AutoCAD Application</h3>
                    <span class="training-date">September 2022</span>
                </div>
                
                <div class="training-item">
                    <h3>Project Planning & Controlling Using Ms. Project</h3>
                    <p>Oil and Gas Case</p>
                    <span class="training-date">September 2022</span>
                </div>
                
                <div class="training-item">
                    <h3>Introduction Rigging and Lifting with Simulation</h3>
                    <p>AutoCAD and Inventor</p>
                    <span class="training-date">August – September 2022</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <div class="container">
            <h2>Skills</h2>
            <div class="skills-container">
                <div class="skills-group">
                    <h3>Technical Skills</h3>
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-file-excel"></i>
                        </div>
                        <div class="skill-detail">
                            <div class="skill-name">Microsoft Office (Word, Excel, PowerPoint, Project)</div>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 95%"></div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-project-diagram"></i>
                        </div>
                        <div class="skill-detail">
                            <div class="skill-name">Primavera P6</div>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 85%"></div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-drafting-compass"></i>
                        </div>
                        <div class="skill-detail">
                            <div class="skill-name">AutoCAD</div>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 90%"></div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-cube"></i>
                        </div>
                        <div class="skill-detail">
                            <div class="skill-name">Autodesk Inventor</div>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 88%"></div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-cubes"></i>
                        </div>
                        <div class="skill-detail">
                            <div class="skill-name">SolidWorks</div>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 85%"></div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-temperature-high"></i>
                        </div>
                        <div class="skill-detail">
                            <div class="skill-name">HTRI</div>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 80%"></div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-cogs"></i>
                        </div>
                        <div class="skill-detail">
                            <div class="skill-name">CAESAR II</div>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 75%"></div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="skills-group">
                    <h3>Languages</h3>
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-language"></i>
                        </div>
                        <div class="skill-detail">
                            <div class="skill-name">Indonesian (Native)</div>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 100%"></div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-language"></i>
                        </div>
                        <div class="skill-detail">
                            <div class="skill-name">English (Proficient)</div>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 85%"></div>
                            </div>
                        </div>
                    </div>
                    
                    <h3 style="margin-top: 2rem;">Certifications</h3>
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-certificate"></i>
                        </div>
                        <div class="skill-detail">
                            <div class="skill-name">Test of English as a Foreign Language (TOEFL)</div>
                            <div class="certificate-number">No. 22.1119.0183.02</div>
                        </div>
                    </div>
                    
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-certificate"></i>
                        </div>
                        <div class="skill-detail">
                            <div class="skill-name">Interpretation Drawing P&ID, Isometrics Layout, Rotating, and Static Equipment</div>
                            <div class="certificate-number">No. GEE/10-2022/TR-16</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <h3>Muhammad Afifani Romadhan</h3>
                <p>Mechanical Engineer | Energy & Emission Data Engineer</p>
                <div class="footer-links">
                    <a href="#home" class="footer-link">Home</a>
                    <a href="#experience" class="footer-link">Experience</a>
                    <a href="#education" class="footer-link">Education</a>
                    <a href="#skills" class="footer-link">Skills</a>
                </div>
                <div class="copyright">
                    &copy; <span id="current-year"></span> Muhammad Afifani Romadhan. All rights reserved.
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Set current year
        document.getElementById('current-year').textContent = new Date().getFullYear();

        // Create floating background dots
        function createDots() {
            const dotsContainer = document.getElementById('dots-bg');
            const numberOfDots = 50;
            
            for (let i = 0; i < numberOfDots; i++) {
                const dot = document.createElement('div');
                dot.className = 'dot';
                
                // Random size between 5px and 20px
                const size = Math.floor(Math.random() * 16) + 5;
                dot.style.width = `${size}px`;
                dot.style.height = `${size}px`;
                
                // Random position
                const posX = Math.floor(Math.random() * 100);
                const posY = Math.floor(Math.random() * 100);
                dot.style.left = `${posX}%`;
                dot.style.top = `${posY}%`;
                
                // Append to container
                dotsContainer.appendChild(dot);
                
                // Animate dot
                animateDot(dot);
            }
        }
        
        function animateDot(dot) {
            const duration = Math.floor(Math.random() * 50) + 30; // Between 30-80 seconds
            const startPosX = parseFloat(dot.style.left);
            const startPosY = parseFloat(dot.style.top);
            
            // Random movement range between -20% and 20%
            const moveRangeX = (Math.random() * 40) - 20;
            const moveRangeY = (Math.random() * 40) - 20;
            
            // Set animation
            dot.style.transition = `transform ${duration}s linear`;
            dot.style.transform = `translate(${moveRangeX}%, ${moveRangeY}%)`;
            
            // When animation ends, start new animation
            setTimeout(() => {
                dot.style.transform = 'translate(0, 0)';
                setTimeout(() => animateDot(dot), duration * 1000);
            }, duration * 1000);
        }
        
        // Initialize tooltip creation
        function createTooltip() {
            const tooltip = document.createElement('div');
            tooltip.className = 'tooltip';
            document.body.appendChild(tooltip);
            return tooltip;
        }
        
        // Show tooltip on element
        function showTooltip(element, text, position = 'top') {
            const tooltip = document.querySelector('.tooltip') || createTooltip();
            tooltip.textContent = text;
            tooltip.className = `tooltip ${position}`;
            
            const rect = element.getBoundingClientRect();
            const tooltipRect = tooltip.getBoundingClientRect();
            
            if (position === 'top') {
                tooltip.style.left = `${rect.left + (rect.width / 2) - (tooltipRect.width / 2)}px`;
                tooltip.style.top = `${rect.top - tooltipRect.height - 10}px`;
            } else if (position === 'bottom') {
                tooltip.style.left = `${rect.left + (rect.width / 2) - (tooltipRect.width / 2)}px`;
                tooltip.style.top = `${rect.bottom + 10}px`;
            }
            
            tooltip.style.opacity = '1';
        }
        
        // Hide tooltip
        function hideTooltip() {
            const tooltip = document.querySelector('.tooltip');
            if (tooltip) {
                tooltip.style.opacity = '0';
            }
        }
        
        // Scroll animation for sections
        function initScrollAnimations() {
            gsap.registerPlugin(ScrollTrigger);
            
            // Timeline items fade in
            gsap.utils.toArray('.timeline-item').forEach((item) => {
                gsap.from(item, {
                    y: 50,
                    opacity: 0,
                    duration: 0.8,
                    scrollTrigger: {
                        trigger: item,
                        start: 'top 85%',
                        end: 'bottom 60%',
                        toggleActions: 'play none none none'
                    }
                });
            });
            
            // Education card fade in
            gsap.from('.education-card', {
                y: 30,
                opacity: 0,
                duration: 0.8,
                scrollTrigger: {
                    trigger: '.education-card',
                    start: 'top 80%',
                    end: 'bottom 70%',
                    toggleActions: 'play none none none'
                }
            });
            
            // Training items fade in and stagger
            gsap.from('.training-item', {
                y: 30,
                opacity: 0,
                duration: 0.6,
                stagger: 0.1,
                scrollTrigger: {
                    trigger: '.training-list',
                    start: 'top 80%',
                    end: 'bottom 60%',
                    toggleActions: 'play none none none'
                }
            });
            
            // Skill progress bars animation
            gsap.utils.toArray('.skill-progress-bar').forEach((bar) => {
                const width = bar.style.width;
                bar.style.width = '0%';
                
                gsap.to(bar, {
                    width: width,
                    duration: 1.5,
                    ease: 'power2.out',
                    scrollTrigger: {
                        trigger: bar,
                        start: 'top 85%',
                        end: 'bottom 70%',
                        toggleActions: 'play none none none'
                    }
                });
            });
        }
        
        // Smooth scroll for navigation links
        function initSmoothScroll() {
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        window.scrollTo({
                            top: target.offsetTop - 70,
                            behavior: 'smooth'
                        });
                    }
                });
            });
        }
        
        // Add interaction to profile photo
        function initProfilePhotoInteraction() {
            const profilePhoto = document.getElementById('profile-photo');
            
            profilePhoto.addEventListener('mouseenter', () => {
                profilePhoto.style.transform = 'scale(1.05)';
                showTooltip(profilePhoto, 'Muhammad Afifani Romadhan', 'bottom');
            });
            
            profilePhoto.addEventListener('mouseleave', () => {
                profilePhoto.style.transform = 'scale(1)';
                hideTooltip();
            });
            
            profilePhoto.addEventListener('click', () => {
                profilePhoto.classList.add('pulse');
                setTimeout(() => {
                    profilePhoto.classList.remove('pulse');
                }, 2000);
            });
        }
        
        // Add interactions to company links
        function initCompanyInteractions() {
            const companies = document.querySelectorAll('.company');
            
            companies.forEach(company => {
                company.addEventListener('mouseenter', () => {
                    showTooltip(company, 'Visit company website', 'bottom');
                });
                
                company.addEventListener('mouseleave', () => {
                    hideTooltip();
                });
            });
        }
        
        // Initialize all functions when DOM is loaded
        document.addEventListener('DOMContentLoaded', () => {
            createDots();
            initScrollAnimations();
            initSmoothScroll();
            initProfilePhotoInteraction();
            initCompanyInteractions();
            
            // Trigger initial animations for above-the-fold content
            gsap.from('.profile-photo', {
                y: 30,
                opacity: 0,
                duration: 1,
                delay: 0.2
            });
            
            gsap.from('.profile-info', {
                y: 30,
                opacity: 0,
                duration: 1,
                delay: 0.5
            });
        });
    </script>
</body>
</html>
