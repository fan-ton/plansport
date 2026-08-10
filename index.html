// База соревнований Russia Running
var eventsData = [
  // Беговые события
  { id: 'rr_1', title: 'Полумарафон «Лужники»', date: '2026-08-23', location: 'Москва', type: 'run', source: 'Russia Running', link: 'https://russiarunning.com' },
  { id: 'rr_2', title: 'Ночной забег', date: '2026-08-29', location: 'Москва', type: 'run', source: 'Russia Running', link: 'https://russiarunning.com' },
  { id: 'rr_3', title: 'Московский Марафон', date: '2026-09-20', location: 'Москва', type: 'run', source: 'Russia Running', link: 'https://russiarunning.com' },
  { id: 'rr_4', title: 'Полумарафон «Моя столица»', date: '2026-10-04', location: 'Москва, Воробьевы горы', type: 'run', source: 'Russia Running', link: 'https://russiarunning.com' },
  { id: 'rr_5', title: 'Сочинский Марафон', date: '2026-11-01', location: 'Сочи', type: 'run', source: 'Russia Running', link: 'https://russiarunning.com' },
  
  // Трейл, плавание, лыжи, вело
  { id: 'rr_6', title: 'Заплыв Swimcup Volga', date: '2026-08-30', location: 'Нижний Новгород', type: 'swim', source: 'Russia Running', link: 'https://russiarunning.com' },
  { id: 'rr_7', title: 'Велогонка Gran Fondo Russia', date: '2026-09-13', location: 'Подмосковье', type: 'bike', source: 'Russia Running', link: 'https://russiarunning.com' },
  { id: 'rr_8', title: 'Осенний кросс-трейл «Лисьи горы»', date: '2026-10-18', location: 'Битцевский лес', type: 'run', source: 'Russia Running', link: 'https://russiarunning.com' },
  { id: 'rr_9', title: 'Лыжный марафон «Европа-Азия»', date: '2026-12-13', location: 'Екатеринбург', type: 'ski', source: 'Russia Running', link: 'https://russiarunning.com' }
];

var favorites = JSON.parse(localStorage.getItem('rr_favs') || '[]');
var currentFilter = 'all';
var selectedDate = null;
var currentCalMonth = 7; // Август (0-индекс)
var currentCalYear = 2026;

var monthNames = ["Январь", "Февраль", "Март", "Апрель", "Май", "Июнь", "Июль", "Август", "Сентябрь", "Октябрь", "Ноябрь", "Декабрь"];

var icons = {
  run: 'fa-person-running',
  ski: 'fa-person-skiing',
  swim: 'fa-person-swimming',
  bike: 'fa-person-biking',
  other: 'fa-trophy'
};

function openSidebar() {
  document.getElementById('sidebar').classList.add('active');
  document.getElementById('overlay').classList.add('active');
}

function closeSidebar() {
  document.getElementById('sidebar').classList.remove('active');
  document.getElementById('overlay').classList.remove('active');
}

function changeMonth(delta) {
  currentCalMonth += delta;
  if (currentCalMonth > 11) {
    currentCalMonth = 0;
    currentCalYear++;
  } else if (currentCalMonth < 0) {
    currentCalMonth = 11;
    currentCalYear--;
  }
  renderCalendarGrid();
}

function renderCalendarGrid() {
  var grid = document.getElementById('calendar-grid');
  var titleEl = document.getElementById('month-title');
  if (!grid || !titleEl) return;

  titleEl.textContent = monthNames[currentCalMonth] + " " + currentCalYear;

  var daysNames = ['Пн', 'Вт', 'Ср', 'Чт', 'Пт', 'Сб', 'Вс'];
  var html = "";
  
  for (var d = 0; d < daysNames.length; d++) {
    html += '<div class="cal-day-name">' + daysNames[d] + '</div>';
  }

  var firstDay = new Date(currentCalYear, currentCalMonth, 1).getDay();
  var emptySlots = (firstDay === 0 ? 6 : firstDay - 1);
  var daysInMonth = new Date(currentCalYear, currentCalMonth + 1, 0).getDate();

  for (var i = 0; i < emptySlots; i++) {
    html += '<div class="cal-date empty"></div>';
  }

  for (var day = 1; day <= daysInMonth; day++) {
    var mStr = (currentCalMonth + 1) < 10 ? '0' + (currentCalMonth + 1) : (currentCalMonth + 1);
    var dStr = day < 10 ? '0' + day : day;
    var dateStr = currentCalYear + '-' + mStr + '-' + dStr;

    var dayEvents = eventsData.filter(function(e) { return e.date === dateStr; });
    var hasEvents = dayEvents.length > 0;
    var isSelected = selectedDate === dateStr;

    var dotsHtml = "";
    for (var k = 0; k < dayEvents.length; k++) {
      dotsHtml += '<div class="event-dot"></div>';
    }

    html += '<div class="cal-date ' + (hasEvents ? 'has-events' : '') + ' ' + (isSelected ? 'selected' : '') + '" onclick="selectDate(\'' + dateStr + '\')">' +
            '<span>' + day + '</span>' +
            '<div class="event-dots">' + dotsHtml + '</div>' +
            '</div>';
  }

  grid.innerHTML = html;
}

function selectDate(dateStr) {
  if (selectedDate === dateStr) {
    clearDateFilter();
  } else {
    selectedDate = dateStr;
    document.getElementById('reset-date').style.display = 'block';
    document.getElementById('date-info-bar').style.display = 'block';
    document.getElementById('selected-date-text').textContent = dateStr.split('-').reverse().join('.');
  }
  closeSidebar();
  renderCalendarGrid();
  renderEvents();
}

function clearDateFilter() {
  selectedDate = null;
  document.getElementById('reset-date').style.display = 'none';
  document.getElementById('date-info-bar').style.display = 'none';
  renderCalendarGrid();
  renderEvents();
}

function toggleFavorite(id) {
  if (favorites.indexOf(id) !== -1) {
    favorites = favorites.filter(function(favId) { return favId !== id; });
  } else {
    favorites.push(id);
  }
  localStorage.setItem('rr_favs', JSON.stringify(favorites));
  updateFavBadge();
  renderEvents();
}

function updateFavBadge() {
  var el = document.getElementById('fav-count');
  if (el) el.textContent = favorites.length;
}

function renderEvents() {
  var container = document.getElementById('events-grid');
  if (!container) return;

  var filtered = eventsData.slice();

  if (currentFilter === 'favorites') {
    filtered = filtered.filter(function(e) { return favorites.indexOf(e.id) !== -1; });
  } else if (currentFilter !== 'all') {
    filtered = filtered.filter(function(e) { return e.type === currentFilter; });
  }

  if (selectedDate) {
    filtered = filtered.filter(function(e) { return e.date === selectedDate; });
  }

  filtered.sort(function(a, b) { return new Date(a.date) - new Date(b.date); });

  if (filtered.length === 0) {
    container.innerHTML = '<div class="empty-msg" style="grid-column: 1/-1;">Стартов по выбранным параметрам не найдено.</div>';
    return;
  }

  var html = "";
  for (var i = 0; i < filtered.length; i++) {
    var event = filtered[i];
    var isFav = favorites.indexOf(event.id) !== -1;
    var iconClass = icons[event.type] || 'fa-trophy';
    var formattedDate = event.date.split('-').reverse().join('.');

    html += '<div class="event-card">' +
              '<div class="card-banner banner-' + event.type + '">' +
                '<i class="fa-solid ' + iconClass + '"></i>' +
                '<button class="fav-btn ' + (isFav ? 'is-fav' : '') + '" onclick="toggleFavorite(\'' + event.id + '\')">' +
                  '<i class="' + (isFav ? 'fa-solid' : 'fa-regular') + ' fa-heart"></i>' +
                '</button>' +
              '</div>' +
              '<div class="card-body">' +
                '<div>' +
                  '<div class="card-meta">' +
                    '<span class="event-date-badge">' + formattedDate + '</span>' +
                    '<span class="event-source">' + event.source + '</span>' +
                  '</div>' +
                  '<div class="event-title">' + event.title + '</div>' +
                '</div>' +
                '<div class="event-location">' +
                  '<i class="fa-solid fa-location-dot"></i> ' + event.location +
                '</div>' +
                '<a href="' + event.link + '" target="_blank" class="register-btn">Зарегистрироваться</a>' +
              '</div>' +
            '</div>';
  }

  container.innerHTML = html;
}

document.addEventListener('DOMContentLoaded', function() {
  var filtersEl = document.getElementById('sport-filters');
  if (filtersEl) {
    filtersEl.addEventListener('click', function(e) {
      var btn = e.target.closest('.filter-btn');
      if (!btn) return;

      var buttons = document.querySelectorAll('.filter-btn');
      for (var i = 0; i < buttons.length; i++) {
        buttons[i].classList.remove('active');
      }
      btn.classList.add('active');

      currentFilter = btn.getAttribute('data-type');
      renderEvents();
    });
  }

  updateFavBadge();
  renderCalendarGrid();
  renderEvents();
});
        
