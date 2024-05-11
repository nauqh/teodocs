---
hide:
  - navigation
---
# Features

## Question forum

Teobot offers a streamlined solution for managing question forum posts within your server. Users can submit their questions through designated forum channels, categorize them based on topics or subjects, and moderators can review and assist in answering your questions.

With features like `tagging`, `searching`, and `sorting`, users can easily navigate through the forum to find relevant questions or contribute answers. The bot ensures an organized and efficient process for sharing knowledge and fostering discussions among community members.

## Exam request
Simplify the process of handling exam requests with the Discord bot's dedicated feature. Users can submit their exam requests specifying details such as the exam name, date, time, and any additional instructions. Moderators can then review and schedule exams accordingly, sending automated notifications to users with the relevant details. 

Additionally, the bot can manage exam registrations, track attendance, and provide reminders to ensure a smooth and well-organized examination process. By centralizing exam management within Discord, the bot enhances communication and coordination for both administrators and participants.

## ER Models

```mermaid
erDiagram
    threads {
        int id PK
        string name
        datetime created_at
        int[] tags
        int[] messages
        int author_id FK
    }

    users {
        int id PK
        string name
        bool is_bot
    }

    user_roles {
        int user_id PK, FK
        int role_id PK, FK
    }

    roles {
        int id PK
        string name
        int position
    }

    users ||--|{ user_roles : has
    roles ||--|{ user_roles : "belongs to"

    users ||--o{ threads : creates
    
    tags {
        int id PK
        string name
    }

    threads ||--|{ tags : has

    messages {
        int id PK
        string content
        datetime created_at
    }

    threads ||--|{ messages : has

```

Using [`SQLAlchemy`](https://docs.sqlalchemy.org/en/20/orm/basic_relationships.html) as ORM to connect with PostgreSQL database allows for efficient management of database interactions. Example of the `Thread` model designed using SQLAlchemy:
```python
class Thread(Base):
    __tablename__ = "threads"

    id: Mapped[str] = mapped_column(primary_key=True)
    name: Mapped[str] = mapped_column(nullable=False)
    created_at: Mapped[datetime] = mapped_column(
        DateTime(timezone=True), server_default=func.now(), nullable=False)
    tags: Mapped[list[str]] = mapped_column(ARRAY(String), nullable=False)
    messages: Mapped[list[str]] = mapped_column(ARRAY(String), nullable=False)

    author_id: Mapped[str] = mapped_column(
        ForeignKey("users.id"), nullable=False)
    author: Mapped["User"] = relationship(back_populates="threads")
```

---

Please note that questions may be ignored if the information can already be found on this wiki.

### **Open an Issue**
If you believe you have found a bug, you can [**open an issue**](). Please do not use the issue page for questions or confusions.

[Join support server](https://discord.gg/hikari){ .md-button }