<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BetMaster - Plataforma de Apostas</title>
    <style>
        :root {
            --primary-color: #1a472a;
            --secondary-color: #2e8b57;
            --accent-color: #00ff7f;
            --dark-color: #0d1f0d;
            --light-color: #f5f5f5;
            --danger-color: #dc3545;
            --warning-color: #ffc107;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #0d1f0d;
            color: var(--light-color);
            min-height: 100vh;
            background-image: linear-gradient(rgba(13, 31, 13, 0.9), rgba(13, 31, 13, 0.9)), 
                              url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect fill="%232e8b57" width="50" height="50"/><rect fill="%232e8b57" x="50" y="50" width="50" height="50"/></svg>');
            background-size: 100px 100px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background-color: var(--primary-color);
            padding: 15px 0;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.5);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 28px;
            font-weight: bold;
            color: var(--accent-color);
            text-shadow: 0 0 10px rgba(0, 255, 127, 0.5);
        }
        
        .logo span {
            color: var(--light-color);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 20px;
        }
        
        nav ul li a {
            color: var(--light-color);
            text-decoration: none;
            font-weight: 500;
            padding: 8px 15px;
            border-radius: 4px;
            transition: all 0.3s ease;
        }
        
        nav ul li a:hover {
            background-color: var(--secondary-color);
        }
        
        .auth-buttons {
            display: flex;
            gap: 10px;
        }
        
        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        
        .btn-primary {
            background-color: var(--accent-color);
            color: var(--dark-color);
        }
        
        .btn-primary:hover {
            background-color: #00cc66;
            transform: translateY(-2px);
        }
        
        .btn-secondary {
            background-color: transparent;
            border: 2px solid var(--accent-color);
            color: var(--accent-color);
        }
        
        .btn-secondary:hover {
            background-color: rgba(0, 255, 127, 0.1);
        }
        
        .btn-danger {
            background-color: var(--danger-color);
            color: white;
        }
        
        .btn-warning {
            background-color: var(--warning-color);
            color: var(--dark-color);
        }
        
        .main-content {
            padding: 40px 0;
        }
        
        .hero {
            text-align: center;
            margin-bottom: 50px;
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            color: var(--accent-color);
        }
        
        .hero p {
            font-size: 20px;
            max-width: 800px;
            margin: 0 auto 30px;
            color: #ccc;
        }
        
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }
        
        .feature-card {
            background-color: rgba(26, 71, 42, 0.6);
            border-radius: 8px;
            padding: 25px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease;
        }
        
        .feature-card:hover {
            transform: translateY(-5px);
        }
        
        .feature-icon {
            font-size: 40px;
            margin-bottom: 15px;
            color: var(--accent-color);
        }
        
        .feature-card h3 {
            margin-bottom: 15px;
            font-size: 22px;
        }
        
        .auth-forms {
            display: none;
            background-color: rgba(26, 71, 42, 0.8);
            border-radius: 8px;
            padding: 30px;
            max-width: 500px;
            margin: 0 auto;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
        }
        
        .auth-forms h2 {
            text-align: center;
            margin-bottom: 25px;
            color: var(--accent-color);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }
        
        .form-group input {
            width: 100%;
            padding: 12px;
            border: 1px solid #2e8b57;
            border-radius: 4px;
            background-color: rgba(0, 0, 0, 0.3);
            color: white;
        }
        
        .form-group input:focus {
            outline: none;
            border-color: var(--accent-color);
        }
        
        .form-actions {
            text-align: center;
        }
        
        .switch-form {
            margin-top: 20px;
            text-align: center;
            color: #ccc;
        }
        
        .switch-form a {
            color: var(--accent-color);
            cursor: pointer;
            text-decoration: underline;
        }
        
        .user-panel {
            display: none;
            background-color: rgba(26, 71, 42, 0.8);
            border-radius: 8px;
            padding: 30px;
            max-width: 800px;
            margin: 0 auto;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
        }
        
        .user-panel h2 {
            text-align: center;
            margin-bottom: 25px;
            color: var(--accent-color);
        }
        
        .balance {
            text-align: center;
            font-size: 32px;
            margin-bottom: 30px;
            color: var(--accent-color);
        }
        
        .transaction-form {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }
        
        footer {
            background-color: var(--primary-color);
            padding: 30px 0;
            text-align: center;
            margin-top: 50px;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .footer-links {
            display: flex;
            gap: 20px;
            margin: 20px 0;
        }
        
        .footer-links a {
            color: #ccc;
            text-decoration: none;
        }
        
        .footer-links a:hover {
            color: var(--accent-color);
        }
        
        .disclaimer {
            max-width: 800px;
            margin: 0 auto;
            font-size: 14px;
            color: #999;
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 15px;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .transaction-form {
                grid-template-columns: 1fr;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .hero p {
                font-size: 18px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <div class="logo">Bet<span>Master</span></div>
            <nav>
                <ul>
                    <li><a href="#">Início</a></li>
                    <li><a href="#">Esportes</a></li>
                    <li><a href="#">Cassino</a></li>
                    <li><a href="#">Promoções</a></li>
                    <li><a href="#">Suporte</a></li>
                </ul>
            </nav>
            <div class="auth-buttons">
                <button class="btn btn-primary" id="loginBtn">Login</button>
                <button class="btn btn-secondary" id="registerBtn">Registrar</button>
            </div>
        </div>
    </header>

    <div class="container main-content">
        <section class="hero">
            <h1>Bem-vindo à BetMaster</h1>
            <p>A plataforma de apostas mais emocionante e segura do mercado. Aproveite odds competitivas, variedade de jogos e promoções exclusivas!</p>
            <button class="btn btn-primary" id="startBtn">Comece a Apostar Agora</button>
        </section>

        <section class="features">
            <div class="feature-card">
                <div class="feature-icon">🎯</div>
                <h3>Variedade de Esportes</h3>
                <p>Aposte em mais de 30 esportes diferentes com odds competitivas e mercados diversificados.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🎰</div>
                <h3>Cassino Ao Vivo</h3>
                <p>Experimente a emoção do cassino com dealers ao vivo e centenas de jogos de slots.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">💰</div>
                <h3>Transações Rápidas</h3>
                <p>Depósitos e saques processados em minutos com total segurança e diversas opções.</p>
            </div>
        </section>

        <div id="loginForm" class="auth-forms">
            <h2>Login</h2>
            <div class="form-group">
                <label for="loginEmail">E-mail</label>
                <input type="email" id="loginEmail" placeholder="Seu e-mail cadastrado">
            </div>
            <div class="form-group">
                <label for="loginPassword">Senha</label>
                <input type="password" id="loginPassword" placeholder="Sua senha">
            </div>
            <div class="form-actions">
                <button class="btn btn-primary" id="doLogin">Entrar</button>
            </div>
            <div class="switch-form">
                Não tem uma conta? <a id="switchToRegister">Registre-se aqui</a>
            </div>
        </div>

        <div id="registerForm" class="auth-forms">
            <h2>Registrar</h2>
            <div class="form-group">
                <label for="registerName">Nome Completo</label>
                <input type="text" id="registerName" placeholder="Seu nome completo">
            </div>
            <div class="form-group">
                <label for="registerEmail">E-mail</label>
                <input type="email" id="registerEmail" placeholder="Seu e-mail">
            </div>
            <div class="form-group">
                <label for="registerPassword">Senha</label>
                <input type="password" id="registerPassword" placeholder="Crie uma senha segura">
            </div>
            <div class="form-group">
                <label for="registerConfirmPassword">Confirmar Senha</label>
                <input type="password" id="registerConfirmPassword" placeholder="Digite novamente sua senha">
            </div>
            <div class="form-actions">
                <button class="btn btn-primary" id="doRegister">Criar Conta</button>
            </div>
            <div class="switch-form">
                Já tem uma conta? <a id="switchToLogin">Faça login aqui</a>
            </div>
        </div>

        <div id="userPanel" class="user-panel">
            <h2>Área do Usuário</h2>
            <div class="balance">
                Saldo: R$ <span id="userBalance">0,00</span>
            </div>
            <div class="transaction-form">
                <div>
                    <h3>Depositar</h3>
                    <div class="form-group">
                        <label for="depositAmount">Valor</label>
                        <input type="number" id="depositAmount" placeholder="R$ 0,00" min="10">
                    </div>
                    <div class="form-group">
                        <label for="depositMethod">Método de Pagamento</label>
                        <select id="depositMethod" class="form-control">
                            <option value="pix">PIX</option>
                            <option value="creditcard">Cartão de Crédito</option>
                            <option value="banktransfer">Transferência Bancária</option>
                        </select>
                    </div>
                    <button class="btn btn-primary" id="doDeposit">Depositar</button>
                </div>
                <div>
                    <h3>Sacar</h3>
                    <div class="form-group">
                        <label for="withdrawAmount">Valor</label>
                        <input type="number" id="withdrawAmount" placeholder="R$ 0,00" min="20">
                    </div>
                    <div class="form-group">
                        <label for="withdrawMethod">Método de Saque</label>
                        <select id="withdrawMethod" class="form-control">
                            <option value="pix">PIX</option>
                            <option value="banktransfer">Transferência Bancária</option>
                        </select>
                    </div>
                    <button class="btn btn-warning" id="doWithdraw">Sacar</button>
                </div>
            </div>
            <div class="form-actions" style="margin-top: 30px;">
                <button class="btn btn-danger" id="logoutBtn">Sair</button>
            </div>
        </div>
    </div>

    <footer>
        <div class="container footer-content">
            <div class="logo">BetMaster</div>
            <div class="footer-links">
                <a href="#">Termos de Uso</a>
                <a href="#">Política de Privacidade</a>
                <a href="#">Jogo Responsável</a>
                <a href="#">Ajuda</a>
                <a href="#">Contato</a>
            </div>
            <div class="disclaimer">
                <p>A BetMaster opera com licença de jogo internacional. Apostas podem ser viciantes. Jogue com responsabilidade. Proibido para menores de 18 anos.</p>
            </div>
        </div>
    </footer>

    <script>
        // Elementos da interface
        const loginBtn = document.getElementById('loginBtn');
        const registerBtn = document.getElementById('registerBtn');
        const startBtn = document.getElementById('startBtn');
        const loginForm = document.getElementById('loginForm');
        const registerForm = document.getElementById('registerForm');
        const userPanel = document.getElementById('userPanel');
        const switchToRegister = document.getElementById('switchToRegister');
        const switchToLogin = document.getElementById('switchToLogin');
        const doLogin = document.getElementById('doLogin');
        const doRegister = document.getElementById('doRegister');
        const doDeposit = document.getElementById('doDeposit');
        const doWithdraw = document.getElementById('doWithdraw');
        const logoutBtn = document.getElementById('logoutBtn');
        const userBalance = document.getElementById('userBalance');
        
        // Estado da aplicação
        let loggedIn = false;
        let balance = 0;
        
        // Event Listeners
        loginBtn.addEventListener('click', () => {
            hideAllForms();
            loginForm.style.display = 'block';
        });
        
        registerBtn.addEventListener('click', () => {
            hideAllForms();
            registerForm.style.display = 'block';
        });
        
        startBtn.addEventListener('click', () => {
            if (loggedIn) {
                // Redirecionaria para os jogos em uma aplicação real
                alert('Redirecionando para os jogos...');
            } else {
                hideAllForms();
                loginForm.style.display = 'block';
            }
        });
        
        switchToRegister.addEventListener('click', () => {
            hideAllForms();
            registerForm.style.display = 'block';
        });
        
        switchToLogin.addEventListener('click', () => {
            hideAllForms();
            loginForm.style.display = 'block';
        });
        
        doLogin.addEventListener('click', () => {
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            
            if (email && password) {
                // Em uma aplicação real, aqui seria uma chamada à API
                loggedIn = true;
                balance = 150.00; // Saldo inicial simulado
                updateUI();
                alert('Login realizado com sucesso!');
            } else {
                alert('Por favor, preencha todos os campos.');
            }
        });
        
        doRegister.addEventListener('click', () => {
            const name = document.getElementById('registerName').value;
            const email = document.getElementById('registerEmail').value;
            const password = document.getElementById('registerPassword').value;
            const confirmPassword = document.getElementById('registerConfirmPassword').value;
            
            if (!name || !email || !password || !confirmPassword) {
                alert('Por favor, preencha todos os campos.');
                return;
            }
            
            if (password !== confirmPassword) {
                alert('As senhas não coincidem.');
                return;
            }
            
            // Em uma aplicação real, aqui seria uma chamada à API
            loggedIn = true;
            balance = 50.00; // Saldo inicial para novos usuários
            updateUI();
            alert('Conta criada com sucesso! Você recebeu R$ 50,00 de bônus.');
        });
        
        doDeposit.addEventListener('click', () => {
            const amount = parseFloat(document.getElementById('depositAmount').value);
            
            if (isNaN(amount) || amount < 10) {
                alert('O valor mínimo para depósito é R$ 10,00.');
                return;
            }
            
            // Em uma aplicação real, aqui seria uma chamada à API/pagamento
            balance += amount;
            updateUI();
            alert(`Depósito de R$ ${amount.toFixed(2)} realizado com sucesso!`);
            document.getElementById('depositAmount').value = '';
        });
        
        doWithdraw.addEventListener('click', () => {
            const amount = parseFloat(document.getElementById('withdrawAmount').value);
            
            if (isNaN(amount) || amount < 20) {
                alert('O valor mínimo para saque é R$ 20,00.');
                return;
            }
            
            if (amount > balance) {
                alert('Saldo insuficiente para realizar o saque.');
                return;
            }
            
            // Em uma aplicação real, aqui seria uma chamada à API
      
