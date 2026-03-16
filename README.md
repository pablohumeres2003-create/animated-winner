
<!DOCTYPE html>
<html lang="es">
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black">
<meta name="apple-mobile-web-app-title" content="Countdown">
<meta charset="UTF-8">
<title>Mi Countdown</title>

<style>
    body {
    font-family: -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif;
    background: #000;
    color: white;
    text-align: center;
    margin-top: 15vh;
}

h1 {
    font-weight: 600;
    letter-spacing: -0.5px;
}

.box {
    font-size: 22px;
    opacity: 0.8;
    margin: 16px;
}

.big {
    font-size: 56px;
    font-weight: 700;
    letter-spacing: -1px;
}
</style>
</head>

<body>

<h1>⏳ hi pablo this is your countdown</h1>

<div class="box" id="today"></div>
<div class="box big" id="counter"></div>
<div class="box" id="remaining"></div>

<script>

const startDate = new Date("2003-07-18");
const endDate   = new Date("2063-07-18");

function updateCountdown() {

    const today = new Date();

    const msPerDay = 1000 * 60 * 60 * 24;

    const totalDays =
        Math.floor((endDate - startDate) / msPerDay);

    const passedDays =
        Math.floor((today - startDate) / msPerDay) + 1;

    const remainingDays = totalDays - passedDays;

    document.getElementById("today").innerHTML =
        "today is: " + today.toLocaleDateString();

    document.getElementById("counter").innerHTML =
        "day " + passedDays + " out of " + totalDays;

    document.getElementById("remaining").innerHTML =
        "there are " + remainingDays + " days left";
}

updateCountdown();

</script>

</body>
</html>
