# City-Dental-Hospital-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CITY DENTAL HOSPITAL - Rajkot's Premier Dental Care</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&family=Playfair+Display:wght@700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #0F3460;
            --secondary: #00A8FF;
            --accent: #FFD700;
            --light-bg: #F5F7FA;
            --white: #FFFFFF;
            --text-dark: #1a1a2e;
            --text-light: #666666;
            --glass: rgba(255, 255, 255, 0.7);
            --glass-border: rgba(255, 255, 255, 0.2);
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', sans-serif;
            color: var(--text-dark);
            line-height: 1.6;
            background: var(--white);
            overflow-x: hidden;
        }

        /* Loading Screen */
        .loader {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--primary) 0%, #0a3a5a 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            animation: fadeOut 0.8s ease-in-out 2s forwards;
        }

        .loader-tooth-icon {
            width: 100px;
            height: 120px;
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            border-radius: 50% 50% 40% 40%;
            margin: 0 auto 30px;
            animation: spin3d 2s linear infinite;
            box-shadow: 0 20px 60px rgba(0, 168, 255, 0.4);
        }

        @keyframes spin3d {
            0% { transform: rotateX(0) rotateY(0) rotateZ(0); }
            100% { transform: rotateX(360deg) rotateY(360deg) rotateZ(360deg); }
        }

        .loader-text {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            color: white;
            font-weight: 800;
            letter-spacing: 3px;
            margin-bottom: 10px;
        }

        .loader-subtext {
            color: var(--secondary);
            font-size: 0.9rem;
            letter-spacing: 2px;
            animation: pulse 1.5s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.6; }
            50% { opacity: 1; }
        }

        @keyframes fadeOut {
            from { opacity: 1; visibility: visible; }
            to { opacity: 0; visibility: hidden; }
        }

        /* Header / Navigation */
        header {
            background: linear-gradient(135deg, var(--primary) 0%, #0a4a67 100%);
            padding: 1.5rem 2rem;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-content {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 2rem;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-weight: 800;
            color: white;
            display: flex;
            align-items: center;
            gap: 0.8rem;
            letter-spacing: -1px;
        }

        .logo-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            box-shadow: 0 4px 15px rgba(0, 168, 255, 0.3);
        }

        /* Tab Navigation */
        .nav-tabs {
            display: flex;
            gap: 1rem;
            list-style: none;
            flex-wrap: wrap;
            justify-content: center;
        }

        .nav-tabs button {
            background: transparent;
            color: rgba(255, 255, 255, 0.8);
            border: 2px solid transparent;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            font-size: 0.95rem;
            transition: all 0.3s ease;
            font-family: 'Poppins', sans-serif;
        }

        .nav-tabs button:hover {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border-color: var(--secondary);
        }

        .nav-tabs button.active {
            background: var(--secondary);
            color: white;
            border-color: var(--secondary);
            box-shadow: 0 4px 15px rgba(0, 168, 255, 0.4);
        }

        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }

            .nav-tabs {
                flex-wrap: wrap;
                justify-content: center;
            }

            .nav-tabs button {
                padding: 0.6rem 1rem;
                font-size: 0.85rem;
            }

            .logo {
                font-size: 1.4rem;
            }
        }

        /* Floating Buttons - FIXED POSITIONING */
        .whatsapp-btn {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 70px;
            height: 70px;
            background: linear-gradient(135deg, #25D366, #20BA5E);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 999;
            box-shadow: 0 8px 25px rgba(37, 211, 102, 0.5);
            animation: float 3s ease-in-out infinite;
            transition: all 0.3s ease;
            text-decoration: none;
        }

        .whatsapp-btn:hover {
            transform: scale(1.15);
            box-shadow: 0 12px 35px rgba(37, 211, 102, 0.7);
        }

        .whatsapp-btn i {
            color: white;
            font-size: 2rem;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
        }

        .floating-appt {
            position: fixed;
            bottom: 120px;
            right: 30px;
            background: linear-gradient(135deg, var(--secondary), #0088CC);
            color: white;
            padding: 1rem 1.5rem;
            border-radius: 50px;
            border: none;
            cursor: pointer;
            font-weight: 700;
            z-index: 999;
            box-shadow: 0 8px 25px rgba(0, 168, 255, 0.5);
            transition: all 0.3s ease;
            font-size: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .floating-appt:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 12px 35px rgba(0, 168, 255, 0.7);
        }

        @media (max-width: 768px) {
            .whatsapp-btn {
                width: 60px;
                height: 60px;
                bottom: 20px;
                right: 20px;
            }
            .whatsapp-btn i {
                font-size: 1.8rem;
            }
            .floating-appt {
                bottom: 90px;
                right: 20px;
                padding: 0.8rem 1.2rem;
                font-size: 0.9rem;
            }
        }

        /* Content Sections */
        .content {
            max-width: 1400px;
            margin: 0 auto;
            padding: 2rem;
            min-height: calc(100vh - 150px);
        }

        .section {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .section.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Home Section */
        .hero {
            min-height: 70vh;
            background: linear-gradient(135deg, #0F3460 0%, #0a4a67 100%);
            border-radius: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-align: center;
            padding: 4rem 2rem;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(0, 168, 255, 0.15) 0%, transparent 70%);
            border-radius: 50%;
        }

        .hero::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(255, 215, 0, 0.1) 0%, transparent 70%);
            border-radius: 50%;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 900px;
        }

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 4rem;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            font-weight: 800;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2.5rem;
            font-weight: 300;
        }

        .hero-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--secondary), #0088CC);
            color: white;
            padding: 1.2rem 2.5rem;
            border-radius: 50px;
            border: none;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 25px rgba(0, 168, 255, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 35px rgba(0, 168, 255, 0.5);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            padding: 1.2rem 2.5rem;
            border-radius: 50px;
            border: 2px solid white;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-secondary:hover {
            background: white;
            color: var(--primary);
        }

        /* Stats Section */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 2rem;
            margin-top: 4rem;
        }

        .stat-card {
            text-align: center;
            padding: 2.5rem 2rem;
            background: var(--glass);
            border-radius: 20px;
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.95);
        }

        .stat-number {
            font-family: 'Playfair Display', serif;
            font-size: 3.2rem;
            font-weight: 800;
            color: var(--secondary);
            margin-bottom: 0.8rem;
            line-height: 1;
        }

        .stat-label {
            color: var(--text-dark);
            font-weight: 600;
            font-size: 1rem;
        }

        /* Section Title */
        .section-title {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            text-align: center;
            color: var(--primary);
            margin-bottom: 1rem;
            font-weight: 800;
        }

        .section-subtitle {
            text-align: center;
            color: var(--text-light);
            font-size: 1.1rem;
            margin-bottom: 3rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        /* About Section */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
            margin-top: 2rem;
        }

        .about-image {
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
        }

        .about-image img {
            width: 100%;
            height: auto;
            display: block;
        }

        .about-image video {
            width: 100%;
            height: auto;
            display: block;
            border-radius: 20px;
        }

        .about-content h3 {
            color: var(--secondary);
            font-size: 1.1rem;
            margin: 2rem 0 1rem 0;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .about-content p {
            color: var(--text-light);
            margin-bottom: 1.5rem;
            line-height: 1.8;
            font-size: 0.95rem;
        }

        @media (max-width: 768px) {
            .about-grid {
                grid-template-columns: 1fr;
            }
            .hero h1 {
                font-size: 2.5rem;
            }
            .section-title {
                font-size: 2rem;
            }
        }

        /* Services Grid */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .service-card {
            background: white;
            padding: 2.5rem;
            border-radius: 20px;
            border: 1px solid rgba(0, 168, 255, 0.1);
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--secondary), var(--accent));
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.3s ease;
        }

        .service-card:hover {
            transform: translateY(-10px);
            border-color: var(--secondary);
            box-shadow: 0 20px 50px rgba(0, 168, 255, 0.15);
        }

        .service-card:hover::before {
            transform: scaleX(1);
        }

        .service-icon {
            font-size: 3rem;
            margin-bottom: 1.5rem;
            display: inline-block;
        }

        .service-card h3 {
            color: var(--primary);
            margin-bottom: 1rem;
            font-size: 1.3rem;
            font-weight: 600;
        }

        .service-card p {
            color: var(--text-light);
            line-height: 1.8;
            font-size: 0.95rem;
        }

        /* Gallery Grid */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 15px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
            cursor: pointer;
            height: 280px;
            transition: all 0.3s ease;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .gallery-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(15, 52, 96, 0.6);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .gallery-item:hover .gallery-overlay {
            opacity: 1;
        }

        .gallery-overlay i {
            color: white;
            font-size: 2.5rem;
        }

        /* Contact Form */
        .contact-section {
            background: linear-gradient(135deg, var(--primary) 0%, #0a3a5a 100%);
            color: white;
            padding: 4rem 2rem;
            border-radius: 20px;
            margin-top: 2rem;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            margin-top: 2rem;
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .contact-item {
            display: flex;
            gap: 1.5rem;
        }

        .contact-icon {
            font-size: 2rem;
            color: var(--secondary);
            min-width: 50px;
            text-align: center;
        }

        .contact-item h3 {
            color: var(--secondary);
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .contact-item p {
            color: rgba(255, 255, 255, 0.8);
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-group label {
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: rgba(255, 255, 255, 0.9);
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            padding: 1rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            color: white;
            font-family: inherit;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .form-group input::placeholder,
        .form-group textarea::placeholder {
            color: rgba(255, 255, 255, 0.6);
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            background: rgba(255, 255, 255, 0.15);
            border-color: var(--secondary);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 120px;
        }

        .submit-btn {
            background: linear-gradient(135deg, var(--secondary), #0088CC);
            color: white;
            padding: 1.2rem;
            border: none;
            border-radius: 10px;
            font-weight: 600;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 25px rgba(0, 168, 255, 0.3);
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 35px rgba(0, 168, 255, 0.5);
            
