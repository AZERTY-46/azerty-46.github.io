<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Se connecter</title>
    <style>
        body {
            font-family: "Segoe UI", Arial, sans-serif;
            background-color: #f5f5f5;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .login-box {
            background: white;
            padding: 40px 30px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            width: 380px;
            text-align: center;
        }
        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            font-size: 24px;
            font-weight: 600;
            margin-bottom: 30px;
        }
        .microsoft-logo {
            width: 24px;
            height: 24px;
        }
        input {
            width: 100%;
            padding: 12px;
            margin: 15px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
            font-size: 15px;
        }
        .options {
            text-align: left;
            margin: 10px 0;
        }
        .link {
            color: #0066cc;
            text-decoration: none;
            font-size: 14px;
        }
        .link:hover {
            text-decoration: underline;
        }
        .btn {
            background-color: #0078d4;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 15px;
            margin-top: 20px;
            width: 100%;
        }
        .btn:hover {
            background-color: #106ebe;
        }
    </style>
</head>
<body>

<div class="login-box">
    <div class="logo">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/44/Microsoft_logo.svg/512px-Microsoft_logo.svg.png" 
             alt="Microsoft" class="microsoft-logo">
        Se connecter
    </div>

    <form>
        <input type="text" placeholder="E-mail, téléphone ou identifiant Skype" required>
        
        <div class="options">
            <a href="#" class="link">Options de connexion</a>
        </div>

        <p style="margin: 25px 0 10px 0; font-size: 14px;">
            Pas de compte ? <a href="#" class="link">Créez-en un !</a>
        </p>

        <p style="font-size: 14px;">
            <a href="#" class="link">Votre compte n’est pas accessible ?</a>
        </p>

        <button type="submit" class="btn">Suivant</button>
    </form>
</div>

</body>
</html>
