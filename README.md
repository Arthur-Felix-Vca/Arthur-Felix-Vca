<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arthur Leite Felix | Cybersecurity Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Courier New', monospace;
        }

        :root {
            --bg-primary: #0a0a0a;
            --bg-secondary: #121212;
            --accent-primary: #00ff41;
            --accent-secondary: #008c29;
            --text-primary: #f1f1f1;
            --text-secondary: #a0a0a0;
            --card-bg: #1a1a1a;
            --transition: all 0.3s ease;
        }

        body {
            background-color: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(0, 255, 65, 0.03) 0%, transparent 20%),
                radial-gradient(circle at 90% 80%, rgba(0, 255, 65, 0.03) 0%, transparent 20%);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            padding: 40px 0;
            text-align: center;
            position: relative;
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid var(--accent-primary);
            box-shadow: 0 0 20px rgba(0, 255, 65, 0.3);
            margin-bottom: 20px;
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            color: var(--accent-primary);
            text-shadow: 0 0 10px rgba(0, 255, 65, 0.5);
        }

        .subtitle {
            font-size: 1.2rem;
            color: var(--text-secondary);
            margin-bottom: 20px;
        }

        .tabs-container {
            margin: 40px 0;
        }

        .tabs {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 30px;
        }

        .tab {
            padding: 12px 24px;
            background-color: var(--bg-secondary);
            border: 1px solid var(--accent-secondary);
            border-radius: 30px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: bold;
            color: var(--text-secondary);
        }

        .tab:hover {
            background-color: var(--accent-secondary);
            color: var(--text-primary);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 140, 41, 0.3);
        }

        .tab.active {
            background-color: var(--accent-primary);
            color: var(--bg-primary);
            border-color: var(--accent-primary);
            box-shadow: 0 0 15px rgba(0, 255, 65, 0.5);
        }

        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease forwards;
            background-color: var(--card-bg);
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.5);
            border: 1px solid #2a2a2a;
        }

        .tab-content.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .skill-card {
            background-color: var(--bg-secondary);
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid var(--accent-primary);
            transition: var(--transition);
        }

        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }

        .skill-card h3 {
            color: var(--accent-primary);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .progress-bar {
            height: 8px;
            background-color: #2a2a2a;
            border-radius: 4px;
            overflow: hidden;
            margin-top: 10px;
        }

        .progress {
            height: 100%;
            background-color: var(--accent-primary);
            border-radius: 4px;
            width: 0;
            transition: width 1s ease;
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 20px;
        }

        .project-card {
            background-color: var(--bg-secondary);
            border-radius: 10px;
            overflow: hidden;
            transition: var(--transition);
            border: 1px solid #2a2a2a;
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
            border-color: var(--accent-secondary);
        }

        .project-img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            border-bottom: 2px solid var(--accent-primary);
        }

        .project-content {
            padding: 20px;
        }

        .project-content h3 {
            color: var(--accent-primary);
            margin-bottom: 10px;
        }

        .project-content p {
            color: var(--text-secondary);
            margin-bottom: 15px;
            font-size: 0.9rem;
        }

        .tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 15px;
        }

        .tag {
            background-color: rgba(0, 255, 65, 0.1);
            color: var(--accent-primary);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
        }

        .btn {
            display: inline-block;
            padding: 8px 16px;
            background-color: transparent;
            color: var(--accent-primary);
            border: 1px solid var(--accent-primary);
            border-radius: 4px;
            text-decoration: none;
            transition: var(--transition);
            font-size: 0.9rem;
        }

        .btn:hover {
            background-color: var(--accent-primary);
            color: var(--bg-primary);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: var(--bg-secondary);
            color: var(--text-primary);
            font-size: 1.5rem;
            transition: var(--transition);
            border: 1px solid #2a2a2a;
        }

        .social-links a:hover {
            background-color: var(--accent-primary);
            color: var(--bg-primary);
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 255, 65, 0.3);
        }

        footer {
            text-align: center;
            padding: 40px 0;
            margin-top: 60px;
            color: var(--text-secondary);
            border-top: 1px solid #2a2a2a;
        }

        .typewriter {
            overflow: hidden;
            border-right: 0.15em solid var(--accent-primary);
            white-space: nowrap;
            margin: 0 auto;
            letter-spacing: 0.15em;
            animation: typing 3.5s steps(40, end), blink-caret 0.75s step-end infinite;
        }

        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: var(--accent-primary) }
        }

        @media (max-width: 768px) {
            .skills-grid, .project-grid {
                grid-template-columns: 1fr;
            }
            
            .tabs {
                flex-direction: column;
                align-items: center;
            }
            
            .tab {
                width: 100%;
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <img src="https://avatars.githubusercontent.com/u/162200251?v=4" alt="Arthur Leite Felix" class="profile-img">
            <h1>Arthur Leite Felix</h1>
            <p class="subtitle">Estudante de Cybersecurity | UESB Vitória da Conquista</p>
            <p class="typewriter"># Hack the planet, secure the future</p>
        </header>

        <div class="tabs-container">
            <div class="tabs">
                <div class="tab active" data-tab="sobre">Sobre Mim</div>
                <div class="tab" data-tab="habilidades">Habilidades</div>
                <div class="tab" data-tab="projetos">Projetos</div>
                <div class="tab" data-tab="certificacoes">Certificações</div>
                <div class="tab" data-tab="contato">Contato</div>
            </div>

            <div class="tab-content active" id="sobre">
                <h2><i class="fas fa-user"></i> Sobre Mim</h2>
                <p>Olá! Sou Arthur Leite Felix, estudante de Cybersecurity na UESB de Vitória da Conquista. Sou apaixonado por segurança cibernética, pentesting e desenvolvimento seguro.</p>
                <p>Atualmente, estou focado em aprimorar minhas habilidades em plataformas como Try Hack Me, Hack The Box e Cybrary, enquanto desenvolvo projetos pessoais relacionados à segurança de sistemas e aplicações.</p>
                <p>Minha jornada na cybersecurity começou com a curiosidade sobre como os sistemas funcionam e como podem ser protegidos contra ameaças. Desde então, tenho me dedicado a aprender sobre vulnerabilidades, exploits e medidas defensivas.</p>
            </div>

            <div class="tab-content" id="habilidades">
                <h2><i class="fas fa-code"></i> Habilidades Técnicas</h2>
                <div class="skills-grid">
                    <div class="skill-card">
                        <h3><i class="fab fa-linux"></i> Linux</h3>
                        <p>Experiência em administração de sistemas Linux, incluindo distribuições como Kali Linux e Ubuntu.</p>
                        <div class="progress-bar">
                            <div class="progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-card">
                        <h3><i class="fas fa-shield-alt"></i> Cybersecurity</h3>
                        <p>Conhecimento em pentesting, análise de vulnerabilidades e técnicas de segurança ofensiva e defensiva.</p>
                        <div class="progress-bar">
                            <div class="progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-card">
                        <h3><i class="fab fa-python"></i> Python</h3>
                        <p>Desenvolvimento de scripts para automação, ferramentas de segurança e análise de dados.</p>
                        <div class="progress-bar">
                            <div class="progress" style="width: 80%"></div>
                        </div>
                    </div>
                    <div class="skill-card">
                        <h3><i class="fab fa-java"></i> Java</h3>
                        <p>Desenvolvimento de aplicações seguras com foco em boas práticas de codificação.</p>
                        <div class="progress-bar">
                            <div class="progress" style="width: 75%"></div>
                        </div>
                    </div>
                    <div class="skill-card">
                        <h3><i class="fas fa-terminal"></i> C++</h3>
                        <p>Desenvolvimento de software de baixo nível e aplicações de alto desempenho.</p>
                        <div class="progress-bar">
                            <div class="progress" style="width: 70%"></div>
                        </div>
                    </div>
                    <div class="skill-card">
                        <h3><i class="fas fa-network-wired"></i> Redes</h3>
                        <p>Compreensão de protocolos de rede, arquiteturas e técnicas de segurança em redes.</p>
                        <div class="progress-bar">
                            <div class="progress" style="width: 80%"></div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="tab-content" id="projetos">
                <h2><i class="fas fa-project-diagram"></i> Projetos em Destaque</h2>
                <div class="project-grid">
                    <div class="project-card">
                        <img src="https://images.unsplash.com/photo-1563089145-599997674d42?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80" alt="Network Scanner" class="project-img">
                        <div class="project-content">
                            <h3>Network Scanner Tool</h3>
                            <p>Ferramenta de varredura de rede desenvolvida em Python para identificar dispositivos e vulnerabilidades.</p>
                            <div class="tags">
                                <span class="tag">Python</span>
                                <span class="tag">Scapy</span>
                                <span class="tag">Networking</span>
                            </div>
                            <a href="#" class="btn">Ver Projeto</a>
                        </div>
                    </div>
                    <div class="project-card">
                        <img src="https://images.unsplash.com/photo-1544890225-2f3faec4cd60?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80" alt="Password Manager" class="project-img">
                        <div class="project-content">
                            <h3>Secure Password Manager</h3>
                            <p>Gerenciador de senhas seguro com criptografia AES-256 desenvolvido em Java.</p>
                            <div class="tags">
                                <span class="tag">Java</span>
                                <span class="tag">Cryptography</span>
                                <span class="tag">Security</span>
                            </div>
                            <a href="#" class="btn">Ver Projeto</a>
                        </div>
                    </div>
                    <div class="project-card">
                        <img src="https://images.unsplash.com/photo-1589652717521-10c0d092dea9?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80" alt="Vulnerability Scanner" class="project-img">
                        <div class="project-content">
                            <h3>Vulnerability Scanner</h3>
                            <p>Scanner de vulnerabilidades para aplicações web com relatórios detalhados.</p>
                            <div class="tags">
                                <span class="tag">Python</span>
                                <span class="tag">Web Security</span>
                                <span class="tag">OWASP</span>
                            </div>
                            <a href="#" class="btn">Ver Projeto</a>
                        </div>
                    </div>
                </div>
            </div>

            <div class="tab-content" id="certificacoes">
                <h2><i class="fas fa-award"></i> Certificações e Conquistas</h2>
                <div class="skills-grid">
                    <div class="skill-card">
                        <h3><i class="fas fa-medal"></i> Try Hack Me</h3>
                        <p>Completei diversos caminhos de aprendizado em cybersecurity, incluindo Pentest+ e Cyber Defense.</p>
                        <div class="progress-bar">
                            <div class="progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-card">
                        <h3><i class="fas fa-medal"></i> Hack The Box</h3>
                        <p>Resolução de máquinas desafiadoras e participação em competições de hacking.</p>
                        <div class="progress-bar">
                            <div class="progress" style="width: 75%"></div>
                        </div>
                    </div>
                    <div class="skill-card">
                        <h3><i class="fas fa-medal"></i> Cybrary</h3>
                        <p>Cursos completos em ethical hacking, análise de malware e segurança de redes.</p>
                        <div class="progress-bar">
                            <div class="progress" style="width: 80%"></div>
                        </div>
                    </div>
                    <div class="skill-card">
                        <h3><i class="fas fa-graduation-cap"></i> UESB</h3>
                        <p>Graduação em andamento com foco em cybersecurity e desenvolvimento seguro.</p>
                        <div class="progress-bar">
                            <div class="progress" style="width: 70%"></div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="tab-content" id="contato">
                <h2><i class="fas fa-envelope"></i> Entre em Contato</h2>
                <p>Estou sempre aberto a discutir novos projetos, oportunidades de colaboração ou conversas sobre cybersecurity.</p>
                <p>Você pode me encontrar nas seguintes plataformas:</p>
                
                <div class="social-links">
                    <a href="#" title="GitHub"><i class="fab fa-github"></i></a>
                    <a href="#" title="LinkedIn"><i class="fab fa-linkedin"></i></a>
                    <a href="#" title="Try Hack Me"><i class="fas fa-code"></i></a>
                    <a href="#" title="Hack The Box"><i class="fas fa-cube"></i></a>
                    <a href="#" title="Email"><i class="fas fa-envelope"></i></a>
                </div>
            </div>
        </div>

        <footer>
            <p>&copy; 2023 Arthur Leite Felix - Cybersecurity Portfolio</p>
            <p>Desenvolvido com &#10084; e muito café</p>
        </footer>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Tab switching functionality
            const tabs = document.querySelectorAll('.tab');
            const tabContents = document.querySelectorAll('.tab-content');
            
            tabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    const tabId = tab.getAttribute('data-tab');
                    
                    // Remove active class from all tabs and contents
                    tabs.forEach(t => t.classList.remove('active'));
                    tabContents.forEach(c => c.classList.remove('active'));
                    
                    // Add active class to clicked tab and corresponding content
                    tab.classList.add('active');
                    document.getElementById(tabId).classList.add('active');
                });
            });
            
            // Animate progress bars when they become visible
            const progressBars = document.querySelectorAll('.progress');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const width = entry.target.style.width;
                        entry.target.style.width = '0';
                        setTimeout(() => {
                            entry.target.style.width = width;
                        }, 100);
                        observer.unobserve(entry.target);
                    }
                });
            }, { threshold: 0.5 });
            
            progressBars.forEach(bar => {
                observer.observe(bar);
            });
        });
    </script>
</body>
</html>
