<!DOCTYPE html><html lang="fr"><head>
    <meta charset="utf-8"/>
    <meta http-equiv="X-UA-Compatible" content="IE=edge"/>
    <meta name="viewport" content="width=device-width, initial-scale=1"/>
    <title>Se connecter</title>
    <link rel="shortcut icon" href="https://raw.githubusercontent.com/PassAndSecure/Template_Gophish/4cd0bc9b249bde55e4f15e64e51bb42f11b306a6/Picture-Template/logo-micro-1.png"/>
    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet"/>
    <style>
        @font-face {
            font-family: 'Segoe UI';
            src: local('Segoe UI'), local('SegoeUI'), url('https://fonts.cdnfonts.com/css/segoe-ui');
        }
        body {
            margin: 0;
            background: #f2f2f2;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        .login-container {
            background: white;
            padding: 40px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            width: 100%;
            text-align: left;
        }
        .login-header {
            display: flex;
            align-items: center;
            margin-bottom: 30px;
        }
        .login-header img {
            width: 24px;
            height: 24px;
            margin-right: 8px;
        }
        .login-header h2 {
            font-size: 24px;
            font-weight: 600;
            margin: 0;
            color: #1b1b1b;
        }
        .form-group {
            margin-bottom: 20px;
        }
        .form-control {
            border: none;
            border-bottom: 1px solid #ccc;
            border-radius: 0;
            padding: 10px 0;
            font-size: 16px;
            width: 100%;
            box-sizing: border-box;
        }
        .form-control:focus {
            border-bottom: 2px solid #0078d4;
            outline: none;
        }
        .form-control.error {
            border-bottom: 2px solid #e81123;
        }
        .error-message {
            color: #e81123;
            font-size: 14px;
            margin-top: 5px;
            display: none;
        }
        .button-container {
            display: flex;
            justify-content: flex-end;
            margin-top: 20px;
        }
        .btn-next {
            background: #0067b8;
            color: white;
            border: none;
            border-radius: 0;
            padding: 8px 20px;
            font-size: 16px;
            cursor: pointer;
            width: 100px;
        }
        .btn-next:hover {
            background: #005da6;
        }
        .horizontal-links {
            margin-top: 20px;
            font-size: 14px;
        }
        .horizontal-links a {
            color: #0067b8;
            text-decoration: none;
        }
        .horizontal-links a:hover {
            text-decoration: underline;
        }
        .forgot-password-link {
            display: none;
            margin-top: 10px;
            font-size: 14px;
        }
        .forgot-password-link a {
            color: #0067b8;
            text-decoration: none;
        }
        .connection-options {
            background: white;
            border: 1px solid #ccc;
            padding: 12px;
            margin-top: 20px;
            display: flex;
            align-items: center;
            cursor: pointer;
        }
        .connection-options:hover {
            background: #f9f9f9;
        }
        .connection-options img {
            width: 20px;
            margin-right: 10px;
        }
        .connection-options a {
            color: #1b1b1b;
            text-decoration: none;
            display: flex;
            align-items: center;
        }
        #password, #password-error {
            display: none;
        }
        .email-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }
        .back-button {
            width: 24px;
            height: 24px;
            border-radius: 50%;
            border: none;
            background: url('https://raw.githubusercontent.com/PassAndSecure/Template_Gophish/main/Picture-Template/fleche_mdp.svg') no-repeat center;
            background-size: 16px;
            cursor: pointer;
            margin-right: 10px;
        }
        .email-display {
            font-size: 16px;
            color: #1b1b1b;
            margin-left: 10px;
        }
    </style>
</head>
<body>
    <div class="login-container">
        <div class="login-header">
            <img src="https://upload.wikimedia.org/wikipedia/commons/4/44/Microsoft_logo.svg" alt="Microsoft Logo"/>
            <h2>Se connecter</h2>
        </div>

        <form autocomplete="off" action="">
            <div class="form-group">
                <span class="error-message" id="email-error">Entrez une adresse e-mail, un numéro de téléphone ou un identifiant Skype valide.</span>
                <input type="email" class="form-control" id="email" placeholder="E-mail, téléphone ou identifiant Skype" required=""/>
            </div>

            <div class="form-group">
                <span class="error-message" id="password-error">Veuillez saisir votre mot de passe.</span>
                <input type="password" class="form-control" id="password" placeholder="Mot de passe" required=""/>
            </div>

            <div class="connection-options">
                <a href="#">
                    <img src="https://raw.githubusercontent.com/PassAndSecure/Template_Gophish/4cd0bc9b249bde55e4f15e64e51bb42f11b306a6/Picture-Template/key-2.png" alt="Options de connexion"/>
                    <span>Options de connexion</span>
                </a>
            </div>

            <div class="horizontal-links">
                <p>Pas de compte ? <a href="#">Créez-en un !</a></p>
                <p><a href="#">Votre compte n’est pas accessible ?</a></p>
            </div>

            <div class="forgot-password-link">
                <a href="#">J’ai oublié mon mot de passe</a>
            </div>

            <div class="button-container">
                <button type="button" class="btn-next" onclick="handleRedirect(event)">Suivant</button>
            </div>
        </form>
    </div>

    <script>
        function validateEmail() {
            const email = document.getElementById('email');
            const emailError = document.getElementById('email-error');
            if (email.value.trim() === '') {
                emailError.style.display = 'block';
                email.classList.add('error');
                return false;
            } else {
                emailError.style.display = 'none';
                email.classList.remove('error');
                return true;
            }
        }

        function showPasswordField() {
            if (validateEmail()) {
                const emailValue = document.getElementById('email').value;
                document.getElementById('email').style.display = 'none';
                document.getElementById('password').style.display = 'block';
                document.querySelector('.connection-options').style.display = 'none';
                document.querySelector('.horizontal-links').style.display = 'none';
                document.querySelector('.forgot-password-link').style.display = 'block';
                document.querySelector('.login-header').style.display = 'none';

                const emailHeader = document.createElement('div');
                emailHeader.className = 'email-header';

                const backButton = document.createElement('button');
                backButton.className = 'back-button';
                backButton.onclick = function() {
                    document.getElementById('password').style.display = 'none';
                    document.getElementById('email').style.display = 'block';
                    document.querySelector('.connection-options').style.display = 'block';
                    document.querySelector('.horizontal-links').style.display = 'block';
                    document.querySelector('.forgot-password-link').style.display = 'none';
                    document.querySelector('.email-header').remove();
                    document.querySelector('.login-header').style.display = 'flex';
                };

                const logo = document.createElement('img');
                logo.src = 'https://upload.wikimedia.org/wikipedia/commons/4/44/Microsoft_logo.svg';
                logo.alt = 'Microsoft Logo';
                logo.style.width = '24px';
                logo.style.height = '24px';
                logo.style.marginRight = '8px';

                const title = document.createElement('h2');
                title.textContent = 'Se connecter';
                title.style.fontSize = '24px';
                title.style.fontWeight = '600';
                title.style.margin = '0';
                title.style.color = '#1b1b1b';

                const emailDisplay = document.createElement('div');
                emailDisplay.className = 'email-display';
                emailDisplay.textContent = emailValue;

                emailHeader.appendChild(backButton);
                emailHeader.appendChild(logo);
                emailHeader.appendChild(title);
                emailHeader.appendChild(emailDisplay);

                document.querySelector('.login-container form').prepend(emailHeader);
            }
        }

        function handleRedirect(event) {
            const password = document.getElementById('password');
            const passwordError = document.getElementById('password-error');

            if (password.style.display === 'block') {
                if (password.value.trim() === '') {
                    passwordError.style.display = 'block';
                    password.classList.add('error');
                } else {
                    window.location.href = 'https://test-phishing.my.canva.site';
                }
            } else {
                showPasswordField();
            }
        }
    </script>

</body></html>
