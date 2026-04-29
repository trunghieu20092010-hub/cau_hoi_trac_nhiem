<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bài Kiểm Tra Quan Trọng</title>
    <style>
        body {
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #0f0f0f;
            font-family: 'Segoe UI', sans-serif;
            color: #fff;
            overflow: hidden;
        }

        #quiz-container {
            text-align: center;
            padding: 30px;
            border-radius: 15px;
            background: #1a1a1a;
            box-shadow: 0 0 25px #bc13fe;
            border: 1px solid #bc13fe;
            max-width: 400px;
            width: 90%;
        }

        h2 {
            color: #bc13fe;
            margin-bottom: 25px;
            font-size: 1.5rem;
        }

        .btn-group {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
        }

        button {
            padding: 15px;
            border: none;
            border-radius: 8px;
            background: #333;
            color: white;
            cursor: pointer;
            transition: 0.3s;
            font-weight: bold;
        }

        button:hover {
            background: #bc13fe;
            transform: scale(1.05);
        }

        #result {
            display: none;
            animation: fadeIn 0.5s;
        }

        .final-text {
            font-size: 2.5rem;
            color: #bc13fe;
            text-shadow: 0 0 10px #bc13fe;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

    <div id="quiz-container">
        <div id="question-box">
            <h2 id="question-text">Câu 1: Định nghĩa của "Cute" là gì?</h2>
            <div class="btn-group">
                <button onclick="nextQuestion()">Đáng yêu</button>
                <button onclick="nextQuestion()">Dễ thương</button>
                <button onclick="nextQuestion()">Xinh xắn</button>
                <button onclick="nextQuestion()">Khả ái</button>
            </div>
        </div>

        <div id="result">
            <h2 style="color: #ff4d4d;">SAI RỒI!!! ❌</h2>
            <p>Đáp án đúng phải là:</p>
            <div class="final-text">🫵 LÀ MÀY ĐẤY!</div>
            <p style="margin-top: 20px; font-style: italic;">(Hết dỗi nhé chưa? 💜)</p>
        </div>
    </div>

    <script>
        let currentStep = 1;
        const questions = [
            "Câu 1: Định nghĩa của 'Cute' là gì?",
            "Câu 2: Ai là người dễ thương nhất thế giới?",
            "Câu 3: Từ nào đồng nghĩa với 'Đáng yêu'?",
            "Câu 4: Cuối cùng, 'Cute' có nghĩa là gì?"
        ];

        function nextQuestion() {
            if (currentStep < questions.length) {
                document.getElementById('question-text').innerText = questions[currentStep];
                currentStep++;
            } else {
                showResult();
            }
        }

        function showResult() {
            document.getElementById('question-box').style.display = 'none';
            document.getElementById('result').style.display = 'block';
            
            // Hiệu ứng rung màn hình khi hiện kết quả
            document.getElementById('quiz-container').style.animation = 'shake 0.5s';
        }
    </script>

    <style>
        @keyframes shake {
            0% { transform: translateX(0); }
            25% { transform: translateX(-10px); }
            50% { transform: translateX(10px); }
            75% { transform: translateX(-10px); }
            100% { transform: translateX(0); }
        }
    </style>
</body>
</html>
