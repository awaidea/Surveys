# 念念不忘，必有回响

**欢迎来到Surveys，在Url后方输入问卷编号开始调查**

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>问卷跳转工具</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 min-h-screen flex items-center justify-center">
    <div class="bg-white p-8 rounded-lg shadow-md w-full max-w-md">
        <h1 class="text-2xl font-bold text-gray-800 mb-6 text-center">问卷跳转工具</h1>
        
        <div class="mb-4">
            <label for="surveyId" class="block text-sm font-medium text-gray-700 mb-2">请输入问卷ID</label>
            <input 
                type="number" 
                id="surveyId" 
                placeholder="例如: 12345" 
                class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
                onkeypress="handleKeyPress(event)"
            >
        </div>
        
        <button 
            id="redirectBtn" 
            class="w-full bg-blue-600 text-white py-2 px-4 rounded-md hover:bg-blue-700 transition duration-200 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2"
            onclick="redirectToSurvey()"
        >
            定向问卷
        </button>
        
        <p class="text-sm text-gray-500 mt-4 text-center">
            转到: <span id="urlPreview" class="text-blue-600">https://survey.catp.cc/</span>
        </p>
    </div>

    <script>
        function redirectToSurvey() {
            const surveyId = document.getElementById('surveyId').value.trim();
            if (surveyId) {
                window.location.href = `https://survey.catp.cc/${surveyId}`;
            } else {
                alert('请输入有效的问卷ID');
            }
        }
        
        function handleKeyPress(event) {
            // 如果按下回车键，执行跳转
            if (event.key === 'Enter') {
                redirectToSurvey();
            }
        }
        
        // 实时更新URL预览
        document.getElementById('surveyId').addEventListener('input', function() {
            const surveyId = this.value.trim();
            const urlPreview = document.getElementById('urlPreview');
            urlPreview.textContent = `https://survey.catp.cc/${surveyId}`;
        });
    </script>
</body>
