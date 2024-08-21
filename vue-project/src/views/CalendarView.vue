<template>
  <div id="container">
    <div id="calendar-header">
      <div id="calendar-button-container">
        <button class="calendar-button">
          <h2>
            < </h2>
        </button>
        <button class="calendar-button">
          <h2>
            > </h2>
        </button>
      </div>
      <h3>Agosto</h3>
    </div>
    <div id="calendar">
      <h2>Aquí van los dias</h2>
    </div>

  </div>
</template>

<style scoped>
#container {
  outline: 2px solid green;
  display: flex;
  flex-direction: column;
  flex: 1;
  height: 100%;
}

#calendar-header {
  display: flex;
  flex-direction: row;
  padding: 10px 15px;
  gap: 10px;
  align-content: center;
  align-items: center;
}

#calendar-button-container {
  display: flex;
  gap: 5px;

}

.calendar-button {
  border: 1px solid #bababa;
  background-color: #f4f4f4;
  border-radius: 3px;
}

#calendar {
  outline: 2px solid red;
  display: flex;
  flex-direction: column;
  height: 100%;
  flex: 1;
}
</style>