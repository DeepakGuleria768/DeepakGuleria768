
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Android Developer README Template</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            max-width: 100%;
            margin: 0;
            padding: 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .readme-container {
            background: white;
            border-radius: 15px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            padding: 40px;
            margin: 0 auto;
            max-width: 900px;
            animation: fadeInUp 1s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
            padding: 30px 0;
            background: linear-gradient(135deg, #3DDC84 0%, #1976D2 100%);
            border-radius: 10px;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: repeating-linear-gradient(
                45deg,
                transparent,
                transparent 10px,
                rgba(255,255,255,0.1) 10px,
                rgba(255,255,255,0.1) 20px
            );
            animation: slide 20s linear infinite;
        }

        @keyframes slide {
            0% { transform: translateX(-50px) translateY(-50px); }
            100% { transform: translateX(50px) translateY(50px); }
        }

        .header-content {
            position: relative;
            z-index: 1;
        }

        .profile-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            border: 4px solid white;
            margin-bottom: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .typing-animation {
            border-right: 3px solid white;
            white-space: nowrap;
            overflow: hidden;
            animation: typing 3s steps(40, end), blink-caret 0.75s step-end infinite;
        }

        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }

        @keyframes blink-caret {
            from, to { border-color: transparent; }
            50% { border-color: white; }
        }

        .section {
            margin: 30px 0;
            padding: 25px;
            border-radius: 10px;
            background: #f8f9fa;
            border-left: 5px solid #3DDC84;
            transition: all 0.3s ease;
        }

        .section:hover {
            transform: translateX(10px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        .section h2 {
            color: #1976D2;
            margin-bottom: 20px;
            font-size: 24px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }

        .tech-item {
            background: white;
            padding: 15px;
            border-radius: 8px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .tech-item:hover {
            transform: translateY(-5px);
            border-color: #3DDC84;
            box-shadow: 0 10px 25px rgba(61, 220, 132, 0.3);
        }

        .project-card {
            background: white;
            border-radius: 10px;
            padding: 20px;
            margin: 15px 0;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            border-left: 4px solid #1976D2;
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 20px 0;
        }

        .stat-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .stat-card:hover {
            transform: scale(1.05);
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin: 20px 0;
        }

        .contact-link {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 12px 20px;
            background: linear-gradient(135deg, #3DDC84 0%, #1976D2 100%);
            color: white;
            text-decoration: none;
            border-radius: 25px;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .contact-link:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
            color: white;
        }

        .emoji {
            font-size: 1.2em;
            margin-right: 5px;
        }

        .wave {
            animation: wave 2s infinite;
            transform-origin: 70% 70%;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(20deg); }
            75% { transform: rotate(-10deg); }
        }

        .code-block {
            background: #2d3748;
            color: #e2e8f0;
            padding: 20px;
            border-radius: 8px;
            margin: 15px 0;
            font-family: 'Courier New', monospace;
            position: relative;
            overflow-x: auto;
        }

        .code-block::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, #3DDC84, #1976D2);
        }

        .footer {
            text-align: center;
            margin-top: 40px;
            padding: 20px;
            border-top: 2px solid #e9ecef;
            color: #666;
        }

        @media (max-width: 768px) {
            .readme-container {
                padding: 20px;
                margin: 10px;
            }
            
            .tech-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            }
            
            .contact-links {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <div class="readme-container">
        <!-- Header Section -->
        <div class="header">
            <div class="header-content">
                <img src="https://via.placeholder.com/120x120/3DDC84/FFFFFF?text=YourPhoto" alt="Profile Picture" class="profile-img">
                <h1 class="typing-animation">👋 Hi, I'm [Your Name] <span class="wave">👋</span></h1>
                <p style="font-size: 18px; margin: 10px 0;">🚀 Passionate Android Developer | 📱 Mobile App Enthusiast | 💡 Problem Solver</p>
            </div>
        </div>

        <!-- About Section -->
        <div class="section">
            <h2><span class="emoji">👨‍💻</span>About Me</h2>
            <p>Welcome to my GitHub profile! I'm a passionate Android developer with [X] years of experience in creating beautiful, functional, and user-friendly mobile applications. I love turning ideas into reality through clean code and innovative solutions.</p>
            
            <div class="stats-container">
                <div class="stat-card">
                    <h3>5+</h3>
                    <p>Years Experience</p>
                </div>
                <div class="stat-card">
                    <h3>50+</h3>
                    <p>Projects Completed</p>
                </div>
                <div class="stat-card">
                    <h3>100K+</h3>
                    <p>App Downloads</p>
                </div>
                <div class="stat-card">
                    <h3>4.8★</h3>
                    <p>Average Rating</p>
                </div>
            </div>
        </div>

        <!-- Tech Stack Section -->
        <div class="section">
            <h2><span class="emoji">🛠️</span>Tech Stack & Tools</h2>
            
            <h3>📱 Mobile Development</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <div>🤖</div>
                    <strong>Android</strong>
                </div>
                <div class="tech-item">
                    <div>☕</div>
                    <strong>Java</strong>
                </div>
                <div class="tech-item">
                    <div>🎯</div>
                    <strong>Kotlin</strong>
                </div>
                <div class="tech-item">
                    <div>⚡</div>
                    <strong>Flutter</strong>
                </div>
                <div class="tech-item">
                    <div>⚛️</div>
                    <strong>React Native</strong>
                </div>
                <div class="tech-item">
                    <div>🔧</div>
                    <strong>Android Studio</strong>
                </div>
            </div>

            <h3>🏗️ Architecture & Libraries</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <div>🏛️</div>
                    <strong>MVVM</strong>
                </div>
                <div class="tech-item">
                    <div>⚡</div>
                    <strong>Jetpack Compose</strong>
                </div>
                <div class="tech-item">
                    <div>🔄</div>
                    <strong>RxJava</strong>
                </div>
                <div class="tech-item">
                    <div>🗃️</div>
                    <strong>Room Database</strong>
                </div>
                <div class="tech-item">
                    <div>🌐</div>
                    <strong>Retrofit</strong>
                </div>
                <div class="tech-item">
                    <div>🗡️</div>
                    <strong>Dagger/Hilt</strong>
                </div>
            </div>

            <h3>☁️ Backend & Tools</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <div>🔥</div>
                    <strong>Firebase</strong>
                </div>
                <div class="tech-item">
                    <div>🐙</div>
                    <strong>Git</strong>
                </div>
                <div class="tech-item">
                    <div>📊</div>
                    <strong>Analytics</strong>
                </div>
                <div class="tech-item">
                    <div>🎨</div>
                    <strong>Figma</strong>
                </div>
                <div class="tech-item">
                    <div>🚀</div>
                    <strong>CI/CD</strong>
                </div>
                <div class="tech-item">
                    <div>☁️</div>
                    <strong>AWS</strong>
                </div>
            </div>
        </div>

        <!-- Featured Projects -->
        <div class="section">
            <h2><span class="emoji">🚀</span>Featured Projects</h2>
            
            <div class="project-card">
                <h3>📱 Awesome Weather App</h3>
                <p>A beautiful weather application with real-time updates, location-based forecasts, and stunning UI animations. Built with Kotlin and Jetpack Compose.</p>
                <p><strong>Tech:</strong> Kotlin, Jetpack Compose, MVVM, Retrofit, Room</p>
                <div style="margin-top: 10px;">
                    <span style="background: #3DDC84; color: white; padding: 4px 8px; border-radius: 4px; font-size: 12px; margin-right: 5px;">⭐ 1.2k</span>
                    <span style="background: #1976D2; color: white; padding: 4px 8px; border-radius: 4px; font-size: 12px; margin-right: 5px;">🍴 230</span>
                    <span style="background: #FF5722; color: white; padding: 4px 8px; border-radius: 4px; font-size: 12px;">📱 Android</span>
                </div>
            </div>

            <div class="project-card">
                <h3>💰 Expense Tracker Pro</h3>
                <p>A comprehensive expense tracking app with budget management, category-wise analysis, and data visualization. Featured on Google Play Store.</p>
                <p><strong>Tech:</strong> Java, Firebase, Material Design, Charts</p>
                <div style="margin-top: 10px;">
                    <span style="background: #3DDC84; color: white; padding: 4px 8px; border-radius: 4px; font-size: 12px; margin-right: 5px;">⭐ 890</span>
                    <span style="background: #1976D2; color: white; padding: 4px 8px; border-radius: 4px; font-size: 12px; margin-right: 5px;">🍴 156</span>
                    <span style="background: #FF5722; color: white; padding: 4px 8px; border-radius: 4px; font-size: 12px;">📱 Android</span>
                </div>
            </div>

            <div class="project-card">
                <h3>🎵 Music Player Ultimate</h3>
                <p>A feature-rich music player with equalizer, playlist management, and social sharing. Clean architecture with robust offline capabilities.</p>
                <p><strong>Tech:</strong> Kotlin, ExoPlayer, RxJava, Dagger, Custom Views</p>
                <div style="margin-top: 10px;">
                    <span style="background: #3DDC84; color: white; padding: 4px 8px; border-radius: 4px; font-size: 12px; margin-right: 5px;">⭐ 2.1k</span>
                    <span style="background: #1976D2; color: white; padding: 4px 8px; border-radius: 4px; font-size: 12px; margin-right: 5px;">🍴 445</span>
                    <span style="background: #FF5722; color: white; padding: 4px 8px; border-radius: 4px; font-size: 12px;">📱 Android</span>
                </div>
            </div>
        </div>

        <!-- GitHub Stats -->
        <div class="section">
            <h2><span class="emoji">📊</span>GitHub Analytics</h2>
            <div class="code-block">
                <div style="text-align: center;">
                    <p>🔥 GitHub Stats will be displayed here</p>
                    <p>Replace with your actual GitHub stats images:</p>
                    <p>[![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&theme=radical)]</p>
                    <p>[![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=yourusername&layout=compact&theme=radical)]</p>
                </div>
            </div>
        </div>

        <!-- Current Focus -->
        <div class="section">
            <h2><span class="emoji">🎯</span>Current Focus</h2>
            <ul style="list-style: none; padding: 0;">
                <li style="margin: 10px 0;">🚀 Learning <strong>Jetpack Compose</strong> and modern Android development</li>
                <li style="margin: 10px 0;">🔍 Exploring <strong>Kotlin Multiplatform</strong> for cross-platform development</li>
                <li style="margin: 10px 0;">📱 Building <strong>scalable and maintainable</strong> Android applications</li>
                <li style="margin: 10px 0;">🌟 Contributing to <strong>open-source</strong> Android projects</li>
                <li style="margin: 10px 0;">📚 Sharing knowledge through <strong>tech blogs</strong> and tutorials</li>
            </ul>
        </div>

        <!-- Connect Section -->
        <div class="section">
            <h2><span class="emoji">🤝</span>Let's Connect!</h2>
            <p>I'm always excited to collaborate on interesting projects or discuss Android development. Feel free to reach out!</p>
            
            <div class="contact-links">
                <a href="mailto:your.email@example.com" class="contact-link">
                    📧 Email
                </a>
                <a href="https://linkedin.com/in/yourprofile" class="contact-link">
                    💼 LinkedIn
                </a>
                <a href="https://twitter.com/yourhandle" class="contact-link">
                    🐦 Twitter
                </a>
                <a href="https://yourwebsite.com" class="contact-link">
                    🌐 Website
                </a>
                <a href="https://medium.com/@yourhandle" class="contact-link">
                    ✍️ Blog
                </a>
            </div>
        </div>

        <!-- Fun Facts -->
        <div class="section">
            <h2><span class="emoji">🎉</span>Fun Facts</h2>
            <ul style="list-style: none; padding: 0;">
                <li style="margin: 10px 0;">☕ I debug better with coffee</li>
                <li style="margin: 10px 0;">🎮 Gaming enthusiast - love mobile games</li>
                <li style="margin: 10px 0;">📸 Photography hobbyist</li>
                <li style="margin: 10px 0;">🌍 Love traveling and exploring new cultures</li>
                <li style="margin: 10px 0;">🎵 Music lover - always coding with headphones on</li>
            </ul>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>⭐ If you like my work, consider giving a star to my repositories!</p>
            <p>💬 <em>"Code is like humor. When you have to explain it, it's bad."</em> - Cory House</p>
            <p>Made with ❤️ by [Your Name] | Last updated: June 2025</p>
        </div>
    </div>

    <script>
        // Add some interactive elements
        document.addEventListener('DOMContentLoaded', function() {
            // Animate skill cards on scroll
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver(function(entries) {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animation = 'fadeInUp 0.6s ease-out forwards';
                    }
                });
            }, observerOptions);

            // Observe all sections
            document.querySelectorAll('.section').forEach(section => {
                observer.observe(section);
            });

            // Add click effects to tech items
            document.querySelectorAll('.tech-item').forEach(item => {
                item.addEventListener('click', function() {
                    this.style.transform = 'scale(0.95)';
                    setTimeout(() => {
                        this.style.transform = 'translateY(-5px)';
                    }, 150);
                });
            });
        });
    </script>
</body>
</html>
