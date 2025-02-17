<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة مدارس الجمهورية</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            direction: rtl;
            text-align: right;
            margin: 0;
            padding: 0;
            background-color: #f5f5f5;
        }
        header {
            background-color: #004080;
            color: white;
            padding: 20px;
            text-align: center;
        }
        nav {
            background-color: #003366;
            padding: 15px;
            display: flex;
            justify-content: center;
        }
        nav a {
            color: white;
            text-decoration: none;
            margin: 15px;
            padding: 10px;
            font-weight: bold;
        }
        .container {
            padding: 20px;
        }
        .login-form, .register-form, .application-form {
            background-color: white;
            padding: 20px;
            margin: 20px auto;
            width: 300px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px #ccc;
        }
        .login-form input, .register-form input, .application-form input, .application-form select {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .login-form button, .register-form button, .application-form button {
            width: 100%;
            padding: 10px;
            background-color: #004080;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .login-form button:hover, .register-form button:hover, .application-form button:hover {
            background-color: #003366;
        }
        .scholarships, .curriculum, .profile, .school-account {
            background-color: #e6f2ff;
            padding: 20px;
            margin-top: 20px;
            border-radius: 10px;
        }
        .scholarships ul, .curriculum ul {
            list-style-type: none;
            padding: 0;
        }
        .scholarships li, .curriculum li {
            padding: 8px 0;
        }
        .scholarship-detail, .curriculum-detail {
            background-color: white;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 0 10px #ccc;
            margin-top: 20px;
            display: none;
        }
        .scholarship-detail h3, .curriculum-detail h3 {
            margin-bottom: 10px;
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <h1>منصة مدارس الجمهورية</h1>
        <p>إدارة المدارس والمناهج والمنح الدراسية</p>
    </header>

    <!-- Navbar -->
    <nav>
        <a href="#">الرئيسية</a>
        <a href="#">حول المنصة</a>
        <a href="#">المدارس</a>
        <a href="#">الطلاب</a>
        <a href="#curriculum">المناهج</a>
        <a href="#scholarships">المنح الدراسية</a>
        <a href="#login">تسجيل الدخول</a>
        <a href="#register">التسجيل</a>
    </nav>

    <!-- Main Content -->
    <div class="container">
        <h2>مرحبًا بكم في منصة مدارس الجمهورية</h2>
        <p>هذه المنصة تهدف إلى تنظيم العملية التعليمية، وإدارة المدارس، وتوفير المناهج الدراسية والمنح الدراسية للطلاب.</p>
    </div>

    <!-- Login Form -->
    <div id="login" class="login-form">
        <h3>تسجيل الدخول</h3>
        <input type="text" placeholder="اسم المستخدم">
        <input type="password" placeholder="كلمة المرور">
        <button>دخول</button>
    </div>

    <!-- Registration Form -->
    <div id="register" class="register-form">
        <h3>إنشاء حساب جديد</h3>
        <input type="text" placeholder="الاسم الكامل">
        <input type="email" placeholder="البريد الإلكتروني">
        <input type="password" placeholder="كلمة المرور">
        <button>تسجيل</button>
    </div>

    <!-- Scholarships Section -->
    <div id="scholarships" class="scholarships">
        <h3>المنح الدراسية المتاحة</h3>
        <ul>
            <li><a href="#" onclick="showScholarshipDetail('chinaGov')">منح الحكومات الصينية - تفاصيل ورابط التقديم</a></li>
            <li><a href="#" onclick="showScholarshipDetail('chinaProvinces')">منح المقاطعات الصينية - تفاصيل ورابط التقديم</a></li>
            <li><a href="#" onclick="showScholarshipDetail('malaysiaBukhari')">منحة جامعة البخاري (ماليزيا) - تفاصيل ورابط التقديم</a></li>
            <li><a href="#" onclick="showScholarshipDetail('malaysiaPerlis')">منحة جامعة برليس (ماليزيا) - تفاصيل ورابط التقديم</a></li>
            <li><a href="#" onclick="showScholarshipDetail('exchangeProgram')">منح التبادل الثقافي - وزارة التعليم العالي عدن</a></li>
        </ul>
    </div>

    <!-- Curriculum Section -->
    <div id="curriculum" class="curriculum">
        <h2>المناهج الدراسية</h2>
        <p>قم بتنزيل مناهج الجمهورية اليمنية مباشرة من منصة مدارس الجمهورية.</p>
        <ul>
            <li><a href="#">تحميل كتب المرحلة الابتدائية</a></li>
            <li><a href="#">تحميل كتب المرحلة الإعدادية</a></li>
            <li><a href="#">تحميل كتب المرحلة الثانوية</a></li>
        </ul>
    </div>

    <!-- Scholarship Detail Modal -->
    <div id="scholarshipDetail" class="scholarship-detail">
        <h3 id="scholarshipTitle"></h3>
        <p id="scholarshipDetails"></p>
        <p id="scholarshipDeadline"></p>
        <p id="scholarshipLink"></p>
        <button onclick="closeScholarshipDetail()">إغلاق</button>
    </div>

    <!-- Scripts -->
    <script>
        function showScholarshipDetail(scholarshipType) {
            var scholarshipTitle = '';
            var scholarshipDetails = '';
            var scholarshipDeadline = '';
            var scholarshipLink = '';

            if (scholarshipType === 'chinaGov') {
                scholarshipTitle = 'منح الحكومات الصينية';
                scholarshipDetails = 'الشروط: يجب أن يكون المتقدم حاصلًا على شهادة الثانوية العامة أو ما يعادلها، مع إتقان اللغة الصينية أو الإنجليزية.';
                scholarshipDeadline = 'المواعيد: يبدأ التقديم في يناير، وآخر موعد للتقديم في مايو.';
                scholarshipLink = '<a href="http://www.csc.edu.cn" target="_blank">رابط التقديم</a>';
            } else if (scholarshipType === 'chinaProvinces') {
                scholarshipTitle = 'منح المقاطعات الصينية';
                scholarshipDetails = 'الشروط: تختلف الشروط حسب المقاطعة، ولكن عمومًا يجب أن يكون المتقدم خريجًا من المرحلة الثانوية مع إتقان اللغة الصينية أو الإنجليزية.';
                scholarshipDeadline = 'المواعيد: يختلف موعد التقديم حسب المقاطعة.';
                scholarshipLink = '<a href="http://www.csc.edu.cn" target="_blank">رابط التقديم</a>';
            } else if (scholarshipType === 'malaysiaBukhari') {
                scholarshipTitle = 'منحة جامعة البخاري (ماليزيا)';
                scholarshipDetails = 'الشروط: يجب أن يكون المتقدم قد أكمل دراسته الثانوية أو ما يعادلها، مع تقديم شهادة إجادة اللغة الإنجليزية.';
                scholarshipDeadline = 'المواعيد: يبدأ التقديم في مارس، وآخر موعد للتقديم في مايو.';
                scholarshipLink = '<a href="https://www.bukhary.edu.my" target="_blank">رابط التقديم</a>';
            } else if (scholarshipType === 'malaysiaPerlis') {
                scholarshipTitle = 'منحة جامعة برليس (ماليزيا)';
                scholarshipDetails = 'الشروط: يجب أن يكون المتقدم قد أكمل دراسته الثانوية أو ما يعادلها، مع إجادة اللغة الإنجليزية.';
                scholarshipDeadline = 'المواعيد: يبدأ التقديم في يوليو، وآخر موعد للتقديم في أغسطس.';
                scholarshipLink = '<a href="https://www.unimap.edu.my" target="_blank">رابط التقديم</a>';
            } else if (scholarshipType === 'exchangeProgram') {
                scholarshipTitle = 'منح التبادل الثقافي - وزارة التعليم العالي عدن';
                scholarshipDetails = 'الشروط: يجب أن يكون المتقدم من خريجي الثانوية العامة أو ما يعادلها. منح التبادل الثقافي تتيح للطلاب فرصة الدراسة في عدة دول تشمل الصين وروسيا وتركيا.';
                scholarshipDeadline = 'المواعيد: يبدأ التقديم عادة في شهر يوليو، وآخر موعد هو أكتوبر.';
                scholarshipLink = '<a href="http://www.mohe-aden.edu.ye" target="_blank">رابط التقديم</a>';
            }

            document.getElementById('scholarshipTitle').innerText = scholarshipTitle;
            document.getElementById('scholarshipDetails').innerText = scholarshipDetails;
            document.getElementById('scholarshipDeadline').innerText = scholarshipDeadline;
            document.getElementById('scholarshipLink').innerHTML = scholarshipLink;

            document.getElementById('scholarshipDetail').style.display = 'block';
        }

        function closeScholarshipDetail() {
            document.getElementById('scholarshipDetail').style.display = 'none';
        }
    </script>

</body>
</html>
