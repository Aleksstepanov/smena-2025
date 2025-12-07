<!DOCTYPE html>
<html lang="ru">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Фрагмент события</title>
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
      }

      body {
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        background-color: #f5f7fa;
        padding: 20px;
      }

      .event-fragment {
        width: 100%;
        max-width: 850px;
        background-color: white;
        border-radius: 16px;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        border-left: 6px solid #4a6de5;
        overflow: hidden;
        animation: fadeIn 0.6s ease-out;
      }

      .event-header {
        background: linear-gradient(135deg, #4a6de5 0%, #3a5bd9 100%);
        color: white;
        padding: 30px 40px;
      }

      .event-title {
        font-size: 28px;
        font-weight: 700;
        margin-bottom: 15px;
        letter-spacing: 0.5px;
      }

      .event-subtitle {
        font-size: 18px;
        font-weight: 400;
        opacity: 0.9;
        line-height: 1.5;
      }

      .event-content {
        padding: 40px;
      }

      .section-title {
        font-size: 22px;
        color: #2c3e50;
        margin-bottom: 20px;
        padding-bottom: 10px;
        border-bottom: 2px solid #eef2f7;
        font-weight: 600;
      }

      .features {
        display: flex;
        flex-wrap: wrap;
        gap: 25px;
        margin-bottom: 40px;
      }

      .feature {
        flex: 1;
        min-width: 200px;
        padding: 20px;
        background-color: #f8fafd;
        border-radius: 10px;
        transition: transform 0.3s, box-shadow 0.3s;
      }

      .feature:hover {
        transform: translateY(-5px);
        box-shadow: 0 8px 20px rgba(74, 109, 229, 0.15);
      }

      .feature-icon {
        font-size: 24px;
        color: #4a6de5;
        margin-bottom: 12px;
      }

      .feature-title {
        font-size: 18px;
        font-weight: 600;
        color: #2c3e50;
        margin-bottom: 8px;
      }

      .feature-desc {
        color: #5a6c7d;
        line-height: 1.5;
      }

      .program-section {
        margin-top: 30px;
      }

      .program-day {
        margin-bottom: 30px;
        border-radius: 12px;
        overflow: hidden;
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
      }

      .day-header {
        background-color: #4a6de5;
        color: white;
        padding: 18px 25px;
        font-size: 20px;
        font-weight: 600;
      }

      .day-date {
        font-size: 16px;
        opacity: 0.9;
        margin-top: 5px;
      }

      .day-events {
        padding: 0;
        background-color: white;
      }

      .event-item {
        display: flex;
        padding: 18px 25px;
        border-bottom: 1px solid #eef2f7;
        align-items: center;
      }

      .event-item:last-child {
        border-bottom: none;
      }

      .event-time {
        font-weight: 600;
        color: #4a6de5;
        min-width: 120px;
      }

      .event-name {
        color: #2c3e50;
        font-weight: 500;
      }

      .event-item.highlight {
        background-color: #f8fafd;
      }

      @media (max-width: 768px) {
        .features {
          flex-direction: column;
        }

        .event-fragment {
          margin: 10px;
        }

        .event-header,
        .event-content {
          padding: 25px 20px;
        }

        .event-item {
          flex-direction: column;
          align-items: flex-start;
          gap: 5px;
        }

        .event-time {
          min-width: auto;
        }
      }

      @keyframes fadeIn {
        from {
          opacity: 0;
          transform: translateY(20px);
        }
        to {
          opacity: 1;
          transform: translateY(0);
        }
      }
    </style>
  </head>
  <body>
    <div class="event-fragment">
      <div class="event-header">
        <div class="event-title">Что вас ждёт:</div>
        <div class="event-subtitle">
          Присоединяйтесь к нашему мероприятию, чтобы узнать о последних
          тенденциях и инновациях в отрасли
        </div>
      </div>

      <div class="event-content">
        <div class="section-title">Основные активности мероприятия</div>

        <div class="features">
          <div class="feature">
            <div class="feature-icon">🎤</div>
            <div class="feature-title">Выступления ведущих экспертов</div>
            <div class="feature-desc">
              Узнайте от лидеров отрасли о последних трендах и будущих
              направлениях развития
            </div>
          </div>

          <div class="feature">
            <div class="feature-icon">🚀</div>
            <div class="feature-title">Презентации инновационных проектов</div>
            <div class="feature-desc">
              Откройте для себя передовые разработки и технологические решения
            </div>
          </div>

          <div class="feature">
            <div class="feature-icon">🤝</div>
            <div class="feature-title">Обмен опытом и знаниями</div>
            <div class="feature-desc">
              Возможность обсудить идеи и поделиться опытом с коллегами
            </div>
          </div>
        </div>

        <div class="program-section">
          <div class="section-title">Программа мероприятия</div>

          <div class="program-day">
            <div class="day-header">
              День 1
              <div class="day-date">1.02.2026</div>
            </div>
            <div class="day-events">
              <div class="event-item">
                <div class="event-time">09:00 - 10:00</div>
                <div class="event-name">Регистрация участников</div>
              </div>
              <div class="event-item highlight">
                <div class="event-time">10:00 - 10:30</div>
                <div class="event-name">Торжественное открытие мероприятия</div>
              </div>
              <div class="event-item">
                <div class="event-time">10:30 - 12:00</div>
                <div class="event-name">Нетворкинг-сессия</div>
              </div>
              <div class="event-item highlight">
                <div class="event-time">12:00 - 17:00</div>
                <div class="event-name">Основные доклады и выступления</div>
              </div>
            </div>
          </div>

          <div class="program-day">
            <div class="day-header">
              День 2
              <div class="day-date">2.02.2026</div>
            </div>
            <div class="day-events">
              <div class="event-item highlight">
                <div class="event-time">09:30 - 12:30</div>
                <div class="event-name">Питч-сессии инновационных проектов</div>
              </div>
              <div class="event-item">
                <div class="event-time">12:30 - 15:30</div>
                <div class="event-name">Практические воркшопы</div>
              </div>
              <div class="event-item highlight">
                <div class="event-time">15:30 - 16:00</div>
                <div class="event-name">Закрытие мероприятия</div>
              </div>
              <div class="event-item">
                <div class="event-time">16:00 - 16:30</div>
                <div class="event-name">Подведение итогов и награждение</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </body>
</html>
