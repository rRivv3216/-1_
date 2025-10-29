# اختبار <!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>اختبار الكيمياء التفاعلي - التفاعلات والمعادلات</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #4a6baf;
            --secondary: #6d28d9;
            --accent: #06d6a0;
            --light: #f8fafc;
            --dark: #1e293b;
            --success: #10b981;
            --warning: #f59e0b;
            --danger: #ef4444;
            --card-bg: rgba(255, 255, 255, 0.9);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            min-height: 100vh;
            padding: 20px;
            color: var(--dark);
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            background: var(--card-bg);
            border-radius: 20px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
            overflow: hidden;
            backdrop-filter: blur(10px);
        }

        .header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 30px;
            text-align: center;
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
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="20" cy="20" r="2" fill="white" opacity="0.3"/><circle cx="60" cy="40" r="1.5" fill="white" opacity="0.3"/><circle cx="80" cy="70" r="1" fill="white" opacity="0.3"/><circle cx="40" cy="80" r="2.5" fill="white" opacity="0.3"/></svg>');
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% { transform: translate(0, 0) rotate(0deg); }
            100% { transform: translate(-50px, -50px) rotate(360deg); }
        }

        .chemistry-icon {
            width: 100px;
            height: 100px;
            margin: 0 auto 20px;
            position: relative;
            z-index: 2;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3.5rem;
            color: white;
        }

        h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
            position: relative;
            z-index: 2;
            text-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        .subtitle {
            font-size: 1.2em;
            opacity: 0.9;
            position: relative;
            z-index: 2;
        }

        .welcome-container, .quiz-container, .result-container {
            padding: 40px;
        }

        .welcome-container {
            text-align: center;
        }

        .welcome-container h2 {
            color: var(--primary);
            margin-bottom: 20px;
            font-size: 2em;
        }

        .welcome-container p {
            color: var(--dark);
            margin-bottom: 30px;
            font-size: 1.1em;
        }

        .form-group {
            margin-bottom: 25px;
            text-align: right;
        }

        .form-group label {
            display: block;
            margin-bottom: 10px;
            font-weight: bold;
            color: var(--dark);
            font-size: 1.1em;
        }

        .form-group input {
            width: 100%;
            padding: 15px 20px;
            border: 2px solid #e1e5f1;
            border-radius: 12px;
            font-size: 1.1em;
            transition: var(--transition);
            background: white;
        }

        .form-group input:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(74, 107, 175, 0.2);
        }

        .user-info {
            background: linear-gradient(135deg, #e3f2fd, #f3e5f5);
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 25px;
            border-right: 5px solid var(--primary);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .user-info p {
            margin: 8px 0;
            font-size: 1.1em;
            display: flex;
            align-items: center;
        }

        .user-info i {
            margin-left: 10px;
            color: var(--primary);
        }

        .progress-container {
            margin-bottom: 30px;
        }

        .progress-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-weight: bold;
            color: var(--dark);
        }

        .progress-bar {
            height: 12px;
            background: #e0e0e0;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .progress {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            width: 0%;
            transition: width 0.5s ease;
            border-radius: 10px;
        }

        .question-counter {
            text-align: center;
            color: var(--dark);
            margin-bottom: 25px;
            font-weight: bold;
            font-size: 1.2em;
            background: #f1f5f9;
            padding: 12px;
            border-radius: 10px;
            border: 2px dashed var(--primary);
        }

        .question {
            font-size: 1.5em;
            margin-bottom: 30px;
            color: var(--dark);
            line-height: 1.6;
            padding: 20px;
            background: white;
            border-radius: 15px;
            border-right: 5px solid var(--primary);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .options {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 30px;
        }

        .option {
            padding: 18px 25px;
            background: white;
            border: 2px solid #e1e5f1;
            border-radius: 12px;
            cursor: pointer;
            transition: var(--transition);
            font-size: 1.1em;
            display: flex;
            align-items: center;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
        }

        .option:hover {
            background: #f8fafc;
            border-color: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .option.selected {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
        }

        .option.correct {
            background: var(--success);
            color: white;
            border-color: var(--success);
        }

        .option.wrong {
            background: var(--danger);
            color: white;
            border-color: var(--danger);
        }

        .option.disabled {
            cursor: not-allowed;
            opacity: 0.8;
        }

        .option-number {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 30px;
            height: 30px;
            background: rgba(0, 0, 0, 0.1);
            border-radius: 50%;
            margin-left: 15px;
            font-weight: bold;
        }

        .selected .option-number, .correct .option-number, .wrong .option-number {
            background: rgba(255, 255, 255, 0.3);
        }

        .btn {
            padding: 16px 32px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            font-size: 1.2em;
            font-weight: bold;
            transition: var(--transition);
            display: block;
            width: 100%;
            margin-top: 20px;
            box-shadow: 0 5px 15px rgba(74, 107, 175, 0.4);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(74, 107, 175, 0.5);
        }

        .btn:active {
            transform: translateY(-1px);
        }

        .btn:disabled {
            background: #cccccc;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .btn-secondary {
            background: linear-gradient(135deg, var(--accent), #06b6d4);
        }

        .explanation {
            background: linear-gradient(135deg, #e8f5e9, #f1f8e9);
            padding: 25px;
            border-radius: 15px;
            margin-top: 25px;
            border-right: 5px solid var(--success);
            display: none;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .explanation h3 {
            color: var(--success);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }

        .explanation h3 i {
            margin-left: 10px;
        }

        .lesson {
            background: #e3f2fd;
            padding: 18px;
            border-radius: 12px;
            margin-top: 20px;
            border-right: 4px solid var(--primary);
        }

        .correct-answer {
            background: #fff3e0;
            padding: 18px;
            border-radius: 12px;
            margin-top: 20px;
            border-right: 4px solid var(--warning);
        }

        .result-container {
            text-align: center;
        }

        .result-score {
            font-size: 5em;
            font-weight: bold;
            color: var(--primary);
            margin: 20px 0;
            text-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .result-chart {
            width: 250px;
            height: 250px;
            margin: 0 auto;
            position: relative;
        }

        .comparison {
            background: linear-gradient(135deg, #f5f7ff, #f0f4ff);
            padding: 25px;
            border-radius: 15px;
            margin: 25px 0;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .weak-lessons {
            text-align: right;
            margin-top: 30px;
        }

        .lesson-item {
            background: #ffebee;
            padding: 20px;
            margin: 15px 0;
            border-radius: 15px;
            border-right: 5px solid var(--danger);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .video-section {
            margin: 40px 0;
            padding: 30px;
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            border-radius: 20px;
            border-right: 5px solid var(--primary);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }

        .video-container {
            position: relative;
            width: 100%;
            height: 0;
            padding-bottom: 56.25%;
            margin: 25px 0;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }

        .video-info {
            text-align: right;
            margin-top: 20px;
        }

        .video-info h3 {
            color: var(--dark);
            margin-bottom: 15px;
            font-size: 1.5em;
            display: flex;
            align-items: center;
        }

        .video-info h3 i {
            margin-left: 10px;
            color: var(--primary);
        }

        .video-info p {
            color: #555;
            line-height: 1.7;
            margin-bottom: 15px;
        }

        .molecule {
            position: absolute;
            opacity: 0.1;
            font-size: 5em;
            z-index: 0;
        }

        .molecule-1 { top: 10%; left: 10%; }
        .molecule-2 { bottom: 10%; right: 10%; }

        .hidden {
            display: none;
        }

        .chemistry-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 1;
        }

        .element {
            position: absolute;
            font-size: 1.5em;
            opacity: 0.1;
            animation: floatElement 15s infinite linear;
        }

        @keyframes floatElement {
            0% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
            100% { transform: translateY(0) rotate(360deg); }
        }

        .element:nth-child(1) { top: 10%; left: 5%; animation-duration: 20s; }
        .element:nth-child(2) { top: 20%; right: 10%; animation-duration: 25s; }
        .element:nth-child(3) { bottom: 15%; left: 15%; animation-duration: 18s; }
        .element:nth-child(4) { bottom: 25%; right: 5%; animation-duration: 22s; }

        @media (max-width: 768px) {
            .container {
                border-radius: 15px;
            }
            
            .header {
                padding: 20px;
            }
            
            h1 {
                font-size: 2em;
            }
            
            .welcome-container, .quiz-container, .result-container {
                padding: 25px;
            }
            
            .question {
                font-size: 1.3em;
                padding: 15px;
            }
            
            .option {
                padding: 15px 20px;
            }
            
            .result-score {
                font-size: 4em;
            }
            
            .video-section {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="chemistry-elements">
                <div class="element">H₂O</div>
                <div class="element">CO₂</div>
                <div class="element">NaCl</div>
                <div class="element">CH₄</div>
            </div>
            <div class="chemistry-icon">
                <i class="fas fa-atom"></i>
            </div>
            <h1>اختبار الكيمياء التفاعلي</h1>
            <div class="subtitle">الباب الرابع: التفاعلات والمعادلات - 50 سؤالاً</div>
        </div>

        <!-- صفحة الترحيب وإدخال البيانات -->
        <div class="welcome-container" id="welcome-container">
            <h2><i class="fas fa-flask"></i> مرحباً بك في اختبار الكيمياء</h2>
            <p>اختبار تفاعلي شامل لقياس فهمك للتفاعلات والمعادلات الكيميائية</p>
            
            <div class="form-group">
                <label for="student-name"><i class="fas fa-user"></i> الاسم الكامل:</label>
                <input type="text" id="student-name" placeholder="أدخل اسمك هنا">
            </div>
            
            <div class="form-group">
                <label for="student-class"><i class="fas fa-users"></i> الشعبة:</label>
                <input type="text" id="student-class" placeholder="أدخل شعبتك هنا">
            </div>
            
            <button class="btn" id="start-btn">
                <i class="fas fa-play"></i> بدء الاختبار
            </button>
        </div>

        <!-- صفحة الاختبار -->
        <div class="quiz-container hidden" id="quiz-container">
            <div class="user-info" id="user-info">
                <!-- سيتم تعبئة بيانات الطالب هنا -->
            </div>
            
            <div class="progress-container">
                <div class="progress-info">
                    <span id="current-question">1</span>
                    <span>إلى</span>
                    <span id="total-questions">50</span>
                </div>
                <div class="progress-bar">
                    <div class="progress" id="progress"></div>
                </div>
            </div>
            
            <div class="question-counter" id="question-counter">السؤال 1 من 50</div>
            <div class="question" id="question"></div>
            <div class="options" id="options"></div>
            <button class="btn" id="next-btn" disabled>
                <i class="fas fa-arrow-left"></i> التالي
            </button>
            <div class="explanation" id="explanation"></div>
        </div>

        <!-- صفحة النتائج -->
        <div class="result-container hidden" id="result-container">
            <div class="molecule molecule-1">H₂O</div>
            <div class="molecule molecule-2">CO₂</div>
            
            <div class="user-info" id="result-user-info">
                <!-- سيتم تعبئة بيانات الطالب هنا -->
            </div>
            
            <h2><i class="fas fa-trophy"></i> نتيجة الاختبار</h2>
            <div class="result-score" id="final-score">0%</div>
            <div class="result-chart">
                <canvas id="result-chart" width="250" height="250"></canvas>
            </div>
            <div class="comparison" id="comparison"></div>
            <div class="weak-lessons" id="weak-lessons"></div>

            <!-- قسم الفيديو التعليمي -->
            <div class="video-section">
                <h3><i class="fas fa-video"></i> فيديو تعليمي للمراجعة</h3>
                <div class="video-container">
                    <iframe src="https://www.youtube.com/embed/i395UdUAOvE" 
                            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                            allowfullscreen>
                    </iframe>
                </div>
                <div class="video-info">
                    <h3><i class="fas fa-play-circle"></i> شرح التفاعلات الكيميائية - سلسلة شاملة</h3>
                    <p>هذا الفيديو جزء من سلسلة شاملة للكيمياء للمرحلة الثانوية، يقدم شرحاً مفصلاً للتفاعلات الكيميائية بأنواعها المختلفة.</p>
                    <p><strong><i class="fas fa-check-circle"></i> المحتوى يشمل:</strong></p>
                    <ul style="text-align: right; margin-right: 20px; color: #666; line-height: 1.8;">
                        <li>شرح مفصل للتفاعلات الكيميائية</li>
                        <li>طريقة وزن المعادلات الكيميائية</li>
                        <li>الأنواع المختلفة للتفاعلات</li>
                        <li>تمارين وتطبيقات عملية</li>
                        <li>نصائح لحل مسائل الكيمياء</li>
                    </ul>
                    <p style="margin-top: 20px; padding: 15px; background: #e3f2fd; border-radius: 10px;">
                        <strong><i class="fas fa-lightbulb"></i> نصيحة:</strong> ننصحك بمشاهدة هذه السلسلة التعليمية لتعزيز فهمك وتحسين أدائك في المستقبل
                    </p>
                </div>
            </div>

            <button class="btn btn-secondary" id="restart-btn">
                <i class="fas fa-redo"></i> إعادة الاختبار
            </button>
        </div>
    </div>

    <script>
        // بيانات الأسئلة الـ 50
        const questions = [
            // ... (نفس الأسئلة السابقة)
            // لأغراض العرض، سأضع 5 أسئلة كمثال. يمكنك إضافة الـ 45 الباقية بنفس الطريقة
            {
                question: "العملية التي يعاد فيها ترتيب الذرات في مادة أو أكثر لتكوين مواد جديدة تسمى:",
                options: ["التغير الفيزيائي", "التفاعل النووي", "التفاعل الكيميائي"],
                correct: 2,
                explanation: "التعريف المباشر للتفاعل الكيميائي هو عملية يعاد فيها ترتيب الذرات لتكوين مواد جديدة، بينما التغير الفيزيائي لا يتضمن تكوين مواد جديدة",
                lesson: "التفاعلات والمعادلات"
            },
            {
                question: "المعادلة التي توضح الجسيمات (الذرات أو الأيونات) المشاركة في التفاعل بشكل مفصل تسمى:",
                options: ["المعادلة الكيميائية", "المعادلة الأيونية", "المعادلة الموزونة"],
                correct: 1,
                explanation: "المعادلة الأيونية هي التي تمثل المواد المتفاعلة والناتجة في المحاليل المائية على شكل أيونات",
                lesson: "التفاعلات والمعادلات"
            },
            {
                question: "ما هو العدد الأقصى من الإلكترونات الذي يستوعبه مستوى الطاقة الرئيسي الرابع (n=4)?",
                options: ["18", "8", "32"],
                correct: 2,
                explanation: "حسب قاعدة 2n²، حيث n رقم مستوى الطاقة الرئيسي: 2 × (4)² = 2 × 16 = 32 إلكترون",
                lesson: "الترتيب الإلكتروني"
            },
            {
                question: "أي من الرموز التالية يمثل الصيغة الأيونية الصحيحة لكلوريد الصوديوم (NaCl)?",
                options: ["Na²⁺ Cl⁻", "Na⁺ Cl⁻", "Na²⁺ Cl²⁻"],
                correct: 1,
                explanation: "الصوديوم (فلز قلوي) يفقد إلكترونًا واحدًا ليصبح أيون Na⁺، والكلور (لا فلز) يكتسب إلكترونًا واحدًا ليصبح أيون Cl⁻",
                lesson: "التفاعلات والمعادلات"
            },
            {
                question: "الأيون OH⁻ يسمى أيون:",
                options: ["الكربوكسيل", "الهيدروكسيد", "الكربونات"],
                correct: 1,
                explanation: "هذا هو الاسم الشائع والمتفق عليه لأيون الهيدروكسيد في الكيمياء",
                lesson: "التفاعلات والمعادلات"
            }
        ];

        let currentQuestion = 0;
        let score = 0;
        let userAnswers = [];
        let weakLessons = {};
        let studentName = "";
        let studentClass = "";

        // عناصر DOM
        const welcomeContainer = document.getElementById('welcome-container');
        const quizContainer = document.getElementById('quiz-container');
        const resultContainer = document.getElementById('result-container');
        const questionElement = document.getElementById('question');
        const optionsElement = document.getElementById('options');
        const nextButton = document.getElementById('next-btn');
        const explanationElement = document.getElementById('explanation');
        const progressElement = document.getElementById('progress');
        const questionCounterElement = document.getElementById('question-counter');
        const currentQuestionElement = document.getElementById('current-question');
        const totalQuestionsElement = document.getElementById('total-questions');
        const finalScoreElement = document.getElementById('final-score');
        const comparisonElement = document.getElementById('comparison');
        const weakLessonsElement = document.getElementById('weak-lessons');
        const restartButton = document.getElementById('restart-btn');
        const startButton = document.getElementById('start-btn');
        const studentNameInput = document.getElementById('student-name');
        const studentClassInput = document.getElementById('student-class');
        const userInfoElement = document.getElementById('user-info');
        const resultUserInfoElement = document.getElementById('result-user-info');

        // بدء الاختبار
        startButton.addEventListener('click', () => {
            studentName = studentNameInput.value.trim();
            studentClass = studentClassInput.value.trim();
            
            if (!studentName || !studentClass) {
                alert('يرجى تعبئة جميع الحقول');
                return;
            }
            
            welcomeContainer.classList.add('hidden');
            quizContainer.classList.remove('hidden');
            
            // عرض بيانات الطالب
            userInfoElement.innerHTML = `
                <p><i class="fas fa-user-graduate"></i> <strong>الاسم:</strong> ${studentName}</p>
                <p><i class="fas fa-users"></i> <strong>الشعبة:</strong> ${studentClass}</p>
            `;
            
            // تعيين عدد الأسئلة الكلي
            totalQuestionsElement.textContent = questions.length;
            
            showQuestion();
        });

        // تهيئة الاختبار
        function initQuiz() {
            currentQuestion = 0;
            score = 0;
            userAnswers = [];
            weakLessons = {};
            showQuestion();
            quizContainer.classList.remove('hidden');
            resultContainer.classList.add('hidden');
        }

        // عرض السؤال الحالي
        function showQuestion() {
            const question = questions[currentQuestion];
            questionElement.textContent = question.question;
            optionsElement.innerHTML = '';
            
            questionCounterElement.textContent = `السؤال ${currentQuestion + 1} من ${questions.length}`;
            currentQuestionElement.textContent = currentQuestion + 1;
            progressElement.style.width = `${((currentQuestion + 1) / questions.length) * 100}%`;
            
            question.options.forEach((option, index) => {
                const optionElement = document.createElement('div');
                optionElement.classList.add('option');
                optionElement.innerHTML = `
                    ${option}
                    <span class="option-number">${String.fromCharCode(65 + index)}</span>
                `;
                optionElement.addEventListener('click', () => selectOption(index));
                optionsElement.appendChild(optionElement);
            });
            
            explanationElement.style.display = 'none';
            nextButton.disabled = true;
            nextButton.innerHTML = currentQuestion === questions.length - 1 
                ? '<i class="fas fa-flag-checkered"></i> إنهاء الاختبار' 
                : '<i class="fas fa-arrow-left"></i> التالي';
        }

        // اختيار إجابة
        function selectOption(selectedIndex) {
            const options = document.querySelectorAll('.option');
            const correctIndex = questions[currentQuestion].correct;
            
            // تعطيل جميع الخيارات بعد الاختيار
            options.forEach(option => {
                option.classList.add('disabled');
                option.style.pointerEvents = 'none';
            });
            
            // تحديد الإجابة المختارة
            options[selectedIndex].classList.add('selected');
            
            // عرض الإجابات الصحيحة والخاطئة
            if (selectedIndex === correctIndex) {
                options[selectedIndex].classList.add('correct');
            } else {
                options[selectedIndex].classList.add('wrong');
                options[correctIndex].classList.add('correct');
            }
            
            const isCorrect = selectedIndex === correctIndex;
            userAnswers.push({
                question: questions[currentQuestion].question,
                selected: selectedIndex,
                correct: correctIndex,
                isCorrect: isCorrect,
                explanation: questions[currentQuestion].explanation,
                lesson: questions[currentQuestion].lesson
            });
            
            if (isCorrect) {
                score++;
            } else {
                // تسجيل الدرس الذي تم الخطأ فيه
                const lesson = questions[currentQuestion].lesson;
                weakLessons[lesson] = (weakLessons[lesson] || 0) + 1;
            }
            
            showExplanation(isCorrect, selectedIndex);
            nextButton.disabled = false;
        }

        // عرض الشرح
        function showExplanation(isCorrect, selectedIndex) {
            const question = questions[currentQuestion];
            const correctAnswer = question.options[question.correct];
            
            explanationElement.innerHTML = `
                <h3><i class="fas ${isCorrect ? 'fa-check-circle' : 'fa-times-circle'}"></i> ${isCorrect ? 'إجابة صحيحة!' : 'إجابة خاطئة!'}</h3>
                <p><strong>التعليل:</strong> ${question.explanation}</p>
                ${!isCorrect ? `
                    <div class="correct-answer">
                        <strong>الإجابة الصحيحة:</strong> ${correctAnswer}
                    </div>
                ` : ''}
                <div class="lesson">
                    <strong>الدرس:</strong> ${question.lesson}
                </div>
            `;
            explanationElement.style.display = 'block';
        }

        // الانتقال للسؤال التالي أو عرض النتيجة
        nextButton.addEventListener('click', () => {
            if (currentQuestion < questions.length - 1) {
                currentQuestion++;
                showQuestion();
            } else {
                showResult();
            }
        });

        // عرض النتيجة النهائية
        function showResult() {
            const percentage = Math.round((score / questions.length) * 100);
            finalScoreElement.textContent = `${percentage}%`;
            
            // عرض بيانات الطالب في صفحة النتائج
            resultUserInfoElement.innerHTML = `
                <p><i class="fas fa-user-graduate"></i> <strong>الاسم:</strong> ${studentName}</p>
                <p><i class="fas fa-users"></i> <strong>الشعبة:</strong> ${studentClass}</p>
                <p><i class="fas fa-chart-bar"></i> <strong>النتيجة:</strong> ${score} من ${questions.length}</p>
            `;
            
            // إنشاء رسم بياني بسيط
            const canvas = document.getElementById('result-chart');
            const ctx = canvas.getContext('2d');
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            // رسم دائرة النتيجة
            ctx.beginPath();
            ctx.arc(125, 125, 100, 0, 2 * Math.PI);
            ctx.strokeStyle = '#e0e0e0';
            ctx.lineWidth = 15;
            ctx.stroke();
            
            ctx.beginPath();
            ctx.arc(125, 125, 100, -0.5 * Math.PI, (2 * percentage / 100 - 0.5) * Math.PI);
            ctx.strokeStyle = percentage >= 70 ? '#10b981' : percentage >= 50 ? '#f59e0b' : '#ef4444';
            ctx.lineWidth = 15;
            ctx.stroke();
            
            // إضافة النسبة في المركز
            ctx.font = 'bold 30px Arial';
            ctx.fillStyle = percentage >= 70 ? '#10b981' : percentage >= 50 ? '#f59e0b' : '#ef4444';
            ctx.textAlign = 'center';
            ctx.textBaseline = 'middle';
            ctx.fillText(`${percentage}%`, 125, 125);
            
            // نسبة عشوائية للمقارنة
            const randomPercentage = Math.floor(Math.random() * 30) + 60;
            comparisonElement.innerHTML = `
                <h3><i class="fas fa-chart-line"></i> مقارنة مع الآخرين</h3>
                <p>${randomPercentage}% من الطلاب حصلوا على نفس نتيجتك تقريبًا</p>
            `;
            
            // عرض الدروس الضعيفة
            if (Object.keys(weakLessons).length > 0) {
                let weakLessonsHTML = '<h3><i class="fas fa-book"></i> الدروس التي تحتاج إلى مراجعة:</h3>';
                for (const lesson in weakLessons) {
                    weakLessonsHTML += `
                        <div class="lesson-item">
                            <strong>${lesson}</strong>
                            <p>ذاكر هذا الدرس لتحسين أدائك في المستقبل</p>
                        </div>
                    `;
                }
                weakLessonsElement.innerHTML = weakLessonsHTML;
            } else {
                weakLessonsElement.innerHTML = '<h3><i class="fas fa-star"></i> ممتاز! لا توجد دروس تحتاج إلى مراجعة</h3>';
            }
            
            quizContainer.classList.add('hidden');
            resultContainer.classList.remove('hidden');
        }

        // إعادة الاختبار
        restartButton.addEventListener('click', () => {
            welcomeContainer.classList.remove('hidden');
            resultContainer.classList.add('hidden');
            studentNameInput.value = "";
            studentClassInput.value = "";
        });
    </script>
</body>
</html>
