{\rtf1\ansi\ansicpg1252\cocoartf2865
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\fs24 \cf0 const queues = \{\
    high: document.getElementById('highQueue'),\
    medium: document.getElementById('mediumQueue'),\
    low: document.getElementById('lowQueue')\
\};\
\
const processList = [];\
\
function addProcess(name, queue) \{\
    const processDiv = document.createElement('div');\
    processDiv.classList.add('process');\
    processDiv.textContent = name;\
    processDiv.dataset.queue = queue;\
    queues[queue].appendChild(processDiv);\
    processList.push(\{ name, queue, element: processDiv \});\
    document.getElementById('output').textContent = `$\{name\} added to $\{queue\} priority queue.`;\
\}\
\
async function runScheduling() \{\
    if (processList.length === 0) \{\
        document.getElementById('output').textContent = "No processes to schedule!";\
        return;\
    \}\
\
    const cpuSlot = document.getElementById('cpuSlot');\
    cpuSlot.innerHTML = "";\
\
    // Multi-Level Queue order: high -> medium -> low\
    const order = processList\
        .filter(p => p.queue === 'high')\
        .concat(processList.filter(p => p.queue === 'medium'))\
        .concat(processList.filter(p => p.queue === 'low'));\
\
    document.getElementById('output').textContent = "Running processes...";\
\
    let currentTime = 0;\
    const ganttData = [];\
\
    for (let p of order) \{\
        await moveToCPU(p.element, cpuSlot);\
        await sleep(1000); // simulate execution\
        cpuSlot.innerHTML = "";\
\
        // Log Gantt chart entry\
        ganttData.push(\{\
            process: p.name,\
            start: currentTime,\
            end: currentTime + 1\
        \});\
        currentTime += 1;\
    \}\
\
    document.getElementById('output').textContent = \
        "All processes executed according to Multi-Level Queue Scheduling.";\
\
    drawGanttChart(ganttData);\
\
    // Reset queues\
    Object.values(queues).forEach(q => q.innerHTML = `<h3>$\{q.querySelector('h3').textContent\}</h3>`);\
    processList.length = 0;\
\}\
\
function sleep(ms) \{\
    return new Promise(resolve => setTimeout(resolve, ms));\
\}\
\
async function moveToCPU(processDiv, cpuSlot) \{\
    const rectCPU = cpuSlot.getBoundingClientRect();\
    const rectProcess = processDiv.getBoundingClientRect();\
    const dx = rectCPU.left - rectProcess.left + rectCPU.width / 2 - rectProcess.width / 2;\
    const dy = rectCPU.top - rectProcess.top;\
\
    processDiv.style.transform = `translate($\{dx\}px, $\{dy\}px)`;\
    await sleep(500);\
    cpuSlot.appendChild(processDiv);\
    processDiv.style.transform = `translate(0,0)`;\
\}\
\
// \uc0\u55357 \u57318  Draw Gantt Chart\
function drawGanttChart(ganttData) \{\
    const ctx = document.getElementById('ganttChart').getContext('2d');\
    if (!ctx) return;\
\
    // Destroy previous chart if any\
    if (window.ganttChartInstance) \{\
        window.ganttChartInstance.destroy();\
    \}\
\
    const colors = ['#4e79a7', '#f28e2b', '#e15759', '#76b7b2', '#59a14f'];\
\
    const datasets = ganttData.map((d, i) => (\{\
        label: d.process,\
        data: [\{ x: [d.start, d.end], y: d.process \}],\
        backgroundColor: colors[i % colors.length],\
        borderRadius: 5\
    \}));\
\
    window.ganttChartInstance = new Chart(ctx, \{\
        type: 'bar',\
        data: \{ datasets \},\
        options: \{\
            indexAxis: 'y',\
            scales: \{\
                x: \{\
                    type: 'linear',\
                    position: 'top',\
                    title: \{ display: true, text: 'Time' \},\
                    min: 0\
                \},\
                y: \{\
                    title: \{ display: true, text: 'Processes' \}\
                \}\
            \},\
            plugins: \{\
                legend: \{ display: false \},\
                tooltip: \{\
                    callbacks: \{\
                        label: ctx => `$\{ctx.dataset.label\}: $\{ctx.raw.x[0]\} - $\{ctx.raw.x[1]\}`\
                    \}\
                \}\
            \}\
        \}\
    \});\
\}}