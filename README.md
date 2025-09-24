<!DOCTYPE html>
<!-- saved from url=(0175)file:///C:/Users/SHIN%20JIN%20KI/OneDrive/%EC%B2%A8%EB%B6%80%20%ED%8C%8C%EC%9D%BC/%EB%AC%B8%EC%84%9C/%EC%88%98%ED%95%99%20%EC%8B%9C%ED%97%98%EC%A7%80%20%EB%B6%84%EC%84%9D.html -->
<html lang="ko"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>수학 시험지 분석</title>
    <script src="./수학 시험지 분석_files/chart.min.js.다운로드"></script>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }
        
        h1 {
            text-align: center;
            color: #2c3e50;
            margin-bottom: 40px;
            font-size: 2.2em;
            background: linear-gradient(45deg, #3498db, #9b59b6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .chart-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }
        
        .chart-container {
            background: #f8f9fa;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .chart-container:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }
        
        .chart-title {
            font-size: 1.3em;
            font-weight: bold;
            color: #2c3e50;
            margin-bottom: 15px;
            text-align: center;
            border-bottom: 2px solid #3498db;
            padding-bottom: 10px;
        }
        
        .chart-wrapper {
            position: relative;
            height: 300px;
        }
        
        .full-width {
            grid-column: 1 / -1;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        
        .stat-card {
            background: linear-gradient(135deg, #74b9ff, #0984e3);
            color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(116, 185, 255, 0.3);
        }
        
        .stat-number {
            font-size: 2em;
            font-weight: bold;
            margin-bottom: 5px;
        }
        
        .stat-label {
            font-size: 0.9em;
            opacity: 0.9;
        }

        .analysis-section {
            margin-top: 40px;
            padding: 25px;
            background: #f1f3f4;
            border-radius: 10px;
            border-left: 5px solid #e74c3c;
        }

        .analysis-title {
            color: #e74c3c;
            font-size: 1.4em;
            margin-bottom: 15px;
            font-weight: bold;
        }

        .analysis-text {
            color: #2c3e50;
            line-height: 1.6;
            font-size: 1.1em;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>📊 삼성현중학교 3학년 2학기 중간고사 수학 시험지 분석</h1>
        
        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-number">25</div>
                <div class="stat-label">총 문제 수</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">100</div>
                <div class="stat-label">총 배점</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">76%</div>
                <div class="stat-label">삼각비 비중</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">4.0</div>
                <div class="stat-label">평균 배점</div>
            </div>
        </div>

        <div class="chart-grid">
            <div class="chart-container">
                <div class="chart-title">📈 단원별 문제 분포</div>
                <div class="chart-wrapper">
                    <canvas id="unitChart" width="936" height="525" style="display: block; box-sizing: border-box; height: 300px; width: 534.857px;"></canvas>
                </div>
            </div>
            
            <div class="chart-container">
                <div class="chart-title">💯 배점별 문제 분포</div>
                <div class="chart-wrapper">
                    <canvas id="scoreChart" width="936" height="525" style="display: block; box-sizing: border-box; height: 300px; width: 534.857px;"></canvas>
                </div>
            </div>
            
            <div class="chart-container">
                <div class="chart-title">🎯 난이도별 분포</div>
                <div class="chart-wrapper">
                    <canvas id="difficultyChart" width="936" height="525" style="display: block; box-sizing: border-box; height: 300px; width: 534.857px;"></canvas>
                </div>
            </div>
            
            <div class="chart-container">
                <div class="chart-title">📝 문제 유형별 분포</div>
                <div class="chart-wrapper">
                    <canvas id="typeChart" width="936" height="525" style="display: block; box-sizing: border-box; height: 300px; width: 534.857px;"></canvas>
                </div>
            </div>
            
            <div class="chart-container full-width">
                <div class="chart-title">📊 문제별 배점 및 난이도 분석</div>
                <div class="chart-wrapper" style="height: 400px;">
                    <canvas id="detailChart" width="2012" height="700" style="display: block; box-sizing: border-box; height: 400px; width: 1149.71px;"></canvas>
                </div>
            </div>
        </div>

        <div class="analysis-section">
            <div class="analysis-title">🔍 주요 분석 결과</div>
            <div class="analysis-text">
                <strong>1. 단원별 불균형:</strong> 삼각비(76%) vs 이차함수(24%)로 심각한 편중<br>
                <strong>2. 난이도 분포:</strong> 기본(32%) → 응용(56%) → 심화(12%)로 적절한 분포<br>
                <strong>3. 배점 특징:</strong> 4점 문제가 60%로 가장 많아 변별력 확보<br>
                <strong>4. 예상 평균:</strong> 65-70점 (상당히 어려운 수준)
            </div>
        </div>
    </div>

    <script>
        // 공통 설정
        Chart.defaults.font.family = "'Segoe UI', sans-serif";
        Chart.defaults.font.size = 12;

        // 1. 단원별 분포
        const unitCtx = document.getElementById('unitChart').getContext('2d');
        new Chart(unitCtx, {
            type: 'doughnut',
            data: {
                labels: ['이차함수', '삼각비'],
                datasets: [{
                    data: [6, 19],
                    backgroundColor: ['#ff6b6b', '#4ecdc4'],
                    borderWidth: 3,
                    borderColor: '#fff'
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { position: 'bottom' },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                const percentage = ((context.parsed / 25) * 100).toFixed(1);
                                return context.label + ': ' + context.parsed + '문제 (' + percentage + '%)';
                            }
                        }
                    }
                }
            }
        });

        // 2. 배점별 분포
        const scoreCtx = document.getElementById('scoreChart').getContext('2d');
        new Chart(scoreCtx, {
            type: 'bar',
            data: {
                labels: ['3점', '4점', '5점'],
                datasets: [{
                    label: '문제 수',
                    data: [5, 15, 5],
                    backgroundColor: ['#74b9ff', '#0984e3', '#6c5ce7'],
                    borderRadius: 8
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { display: false }
                },
                scales: {
                    y: { beginAtZero: true, max: 16 }
                }
            }
        });

        // 3. 난이도별 분포
        const difficultyCtx = document.getElementById('difficultyChart').getContext('2d');
        new Chart(difficultyCtx, {
            type: 'pie',
            data: {
                labels: ['기본', '응용', '심화'],
                datasets: [{
                    data: [8, 14, 3],
                    backgroundColor: ['#55a3ff', '#ffa726', '#ef5350'],
                    borderWidth: 3,
                    borderColor: '#fff'
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { position: 'bottom' },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                const percentage = ((context.parsed / 25) * 100).toFixed(1);
                                return context.label + ': ' + context.parsed + '문제 (' + percentage + '%)';
                            }
                        }
                    }
                }
            }
        });

        // 4. 문제 유형별 분포
        const typeCtx = document.getElementById('typeChart').getContext('2d');
        new Chart(typeCtx, {
            type: 'radar',
            data: {
                labels: ['개념확인', '계산중심', '그래프해석', '도형응용', '실생활응용', '융합형'],
                datasets: [{
                    label: '문제 수',
                    data: [6, 8, 4, 5, 1, 1],
                    backgroundColor: 'rgba(116, 185, 255, 0.2)',
                    borderColor: '#74b9ff',
                    borderWidth: 2,
                    pointBackgroundColor: '#0984e3',
                    pointBorderColor: '#fff',
                    pointRadius: 6
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                scales: {
                    r: {
                        beginAtZero: true,
                        max: 10,
                        grid: { color: '#e9ecef' },
                        ticks: { stepSize: 2 }
                    }
                },
                plugins: {
                    legend: { display: false }
                }
            }
        });

        // 5. 문제별 상세 분석
        const detailCtx = document.getElementById('detailChart').getContext('2d');
        
        // 문제별 데이터
        const problemData = [];
        const difficultyData = [];
        const colors = [];
        
        for(let i = 1; i <= 25; i++) {
            let score, difficulty, color;
            
            if([1, 7, 11, 15, 19].includes(i)) {
                score = 3;
                difficulty = 1; // 기본
                color = '#55a3ff';
            } else if([5, 6, 17, 23, 24, 25].includes(i)) {
                score = 5;
                difficulty = i >= 23 ? 3 : 2; // 23번 이후는 심화
                color = i >= 23 ? '#ef5350' : '#ffa726';
            } else {
                score = 4;
                difficulty = i <= 10 ? 1 : 2; // 1-10번은 기본, 나머지는 응용
                color = i <= 10 ? '#55a3ff' : '#ffa726';
            }
            
            problemData.push(score);
            difficultyData.push(difficulty);
            colors.push(color);
        }

        new Chart(detailCtx, {
            type: 'bar',
            data: {
                labels: Array.from({length: 25}, (_, i) => `${i+1}번`),
                datasets: [
                    {
                        label: '배점',
                        data: problemData,
                        backgroundColor: colors,
                        borderRadius: 4,
                        yAxisID: 'y'
                    },
                    {
                        label: '난이도',
                        data: difficultyData,
                        type: 'line',
                        borderColor: '#e74c3c',
                        backgroundColor: 'rgba(231, 76, 60, 0.1)',
                        borderWidth: 3,
                        pointRadius: 5,
                        pointBackgroundColor: '#e74c3c',
                        yAxisID: 'y1'
                    }
                ]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { position: 'top' },
                    tooltip: {
                        callbacks: {
                            afterLabel: function(context) {
                                if(context.datasetIndex === 1) {
                                    const levels = ['', '기본', '응용', '심화'];
                                    return '난이도: ' + levels[context.parsed.y];
                                }
                                return '';
                            }
                        }
                    }
                },
                scales: {
                    x: {
                        grid: { display: false }
                    },
                    y: {
                        type: 'linear',
                        display: true,
                        position: 'left',
                        title: { display: true, text: '배점' },
                        max: 6
                    },
                    y1: {
                        type: 'linear',
                        display: true,
                        position: 'right',
                        title: { display: true, text: '난이도' },
                        min: 0,
                        max: 4,
                        ticks: {
                            callback: function(value) {
                                const levels = ['', '기본', '응용', '심화'];
                                return levels[value] || '';
                            }
                        },
                        grid: { drawOnChartArea: false }
                    }
                }
            }
        });
    </script>

</body></html>
