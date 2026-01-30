ก่อนใช้งานร่วมกับ MIkrotik ยกเลิกคอมเม้นด้วยนะจร้าาา 
<html>
<head>
<!-- $(if refresh-timeout) -->
<meta http-equiv="refresh" content="$(refresh-timeout-secs)">
<!-- $(endif) -->
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0" />   
<meta http-equiv="pragma" content="no-cache">
<meta http-equiv="expires" content="-1">
     <link rel="icon" href="img/logoRAM.png" sizes="64x64" type="image/png">

<title>Internet hotspot - Status</title>
<style>
    :root {
        --blue: #0038c6;
        --light-blue: #26a9e0;
        --gray: #e6e7e8;
    }
    
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    
    body {
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        background: #f5f7fa;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 20px;
    }
    
    .ie-fixMinHeight {
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    
    .main {
        width: 100%;
        max-width: 400px;
    }
    
    .wrap {
        background: white;
        padding: 60px 40px;
        border-radius: 16px;
        box-shadow: 0 2px 12px rgba(0, 0, 0, 0.08);
        text-align: center;
    }
    
    .logo {
        width: 100px;
        height: 100px;
        margin: 0 auto 30px;
        display: block;
        object-fit: contain;
    }
    
    h1 {
        color: #2c3e50;
        font-size: 24px;
        margin-bottom: 40px;
        font-weight: 500;
    }
    
    form {
        display: flex;
        flex-direction: column;
        gap: 12px;
    }
    
    button, input[type="submit"] {
        padding: 14px 24px;
        font-size: 15px;
        font-weight: 500;
        border: none;
        border-radius: 8px;
        cursor: pointer;
        transition: all 0.2s ease;
    }
    
    button[type="button"] {
        background: var(--blue);
        color: white;
    }
    
    button[type="button"]:hover {
        background: #002a9e;
        transform: translateY(-1px);
    }
    
    input[type="submit"] {
        background: white;
        color: #666;
        border: 1px solid #ddd;
    }
    
    input[type="submit"]:hover {
        background: #f8f9fa;
        border-color: #ccc;
    }
    
    button:active, input[type="submit"]:active {
        transform: translateY(0);
    }
    
    @media (max-width: 480px) {
        .wrap {
            padding: 50px 30px;
        }
        
        .logo {
            width: 80px;
            height: 80px;
        }
        
        h1 {
            font-size: 22px;
        }
    }
</style>
<script>

$(if advert-pending == 'yes')
    var popup = '';
    function focusAdvert() {
	if (window.focus) popup.focus();
    }
    function openAdvert() {
	popup = open('$(link-advert)', 'hotspot_advert', '');
	setTimeout("focusAdvert()", 1000);
    }
$(endif)
    function openLogout() {
	if (window.name != 'hotspot_status') return true;
        open('$(link-logout)', 'hotspot_logout', 'toolbar=0,location=0,directories=0,status=0,menubars=0,resizable=1,width=280,height=250');
	window.close();
	return false;
    }
</script>
    
</head>
<body $(if advert-pending == 'yes') onLoad="openAdvert()" $(endif)>
    <div class="ie-fixMinHeight">
        <div class="main">
            <div class="wrap">
                <img src="img/logoRAM.png" alt="โรงพยาบาลรามคำแหง" class="logo">
                
                <form action="$(link-logout)" name="logout" onSubmit="return openLogout()">
                    <!-- $(if login-by-mac != 'yes') -->
                    <button type="button" onclick="window.open('https://www.ram-hosp.co.th/th', '_blank')">
                        เข้าสู่เว็บไซต์โรงพยาบาลรามคำแหง
                    </button>
                    
                    <input type="submit" value="ออกจากระบบ">
                    <!-- $(endif) -->
                </form>
            </div>
        </div>
    </div>
</body>
</html>
