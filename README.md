# Suncity
<a href="/boka" class="booking-button">
    Boka tid
</a>
<section class="booking">
    <h1>Boka din soltids</h1>

    <label>Välj datum</label>
    <input type="date" id="date">

    <label>Välj solarium</label>
    <select id="machine">
        <option value="1">Solarium 1</option>
        <option value="2">Solarium 2</option>
        <option value="3">Solarium 3</option>
        <option value="4">Solarium 4</option>
    </select>

    <label>Välj tid</label>
    <div id="times"></div>

    <button id="bookButton">
        Boka vald tid
    </button>
</section>
async function getAvailableTimes(date, machine) {
    const response = await fetch(
        `/api/available?date=${date}&machine=${machine}`
    );

    const data = await response.json();

    return data.times;
}
