# 重新导向

将在5秒内自动跳转，[立即跳转](https://forms.cloud.microsoft/r/z7vXhCLs7u)

<script>
// 倒计时重定向函数
function redirectAfterCountdown(url, seconds) {
    // 参数验证
    if (!url || typeof url !== 'string') {
        console.error('无效的重定向URL');
        return;
    }
    
    if (isNaN(seconds) || seconds <= 0) {
        console.error('倒计时秒数必须为正数');
        return;
    }
    
    // 倒计时逻辑
    const countdown = function() {
        if (seconds <= 0) {
            window.location.href = url;
            return;
        }
        
        seconds--;
        setTimeout(countdown, 1000);
    };
    
    // 开始倒计时
    countdown();
}

// 3秒后跳转
redirectAfterCountdown('https://forms.cloud.microsoft/r/z7vXhCLs7u', 3);
</script>
