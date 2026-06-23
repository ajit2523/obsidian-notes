## __Interfaces__
**Interfaces** define what a component should do, **not how** it should do it
an **interface** is a **contract:** a list of methods that any implementing class _must_ provide. It specifies a set of behaviors that a class agrees to implement but leaves the _details_ of those behaviors up to each implementation.
```java
interface NotificationService {
    void send(String recipient, String message);
}

class EmailNotifier implements NotificationService {
    public void send(String recipient, String message) {
        System.out.println("[Email] To: " + recipient + " | " + message);
    }
}

class SlackNotifier implements NotificationService {
    public void send(String recipient, String message) {
        System.out.println("[Slack] Channel: " + recipient + " | " + message);
    }
}

class WebhookNotifier implements NotificationService {
    public void send(String recipient, String message) {
        System.out.println("[Webhook] URL: " + recipient + " | " + message);
    }
}

class AlertService {
    private NotificationService notifier;

    public AlertService(NotificationService notifier) {
        this.notifier = notifier;
    }

    public void triggerAlert(String recipient, String issue) {
        String alertMessage = "ALERT: " + issue;
        notifier.send(recipient, alertMessage);
    }
}

// Usage
public class Main {
    public static void main(String[] args) {
        AlertService emailAlerts = new AlertService(new EmailNotifier());
        emailAlerts.triggerAlert("ops@company.com", "CPU usage at 95%");

        AlertService slackAlerts = new AlertService(new SlackNotifier());
        slackAlerts.triggerAlert("#incidents", "Database connection pool exhausted");

        AlertService webhookAlerts = new AlertService(new WebhookNotifier());
        webhookAlerts.triggerAlert("https://hooks.example.com/alerts", "Disk usage at 90%");
    }
}
```

## __Encapsulation__
**Encapsulation** is the practice of **grouping data (variables) and behavior (methods)** that operate on that data into a single unit (typically a class) and **restricting direct access to the internal details** of that class.
>**Encapsulation = Data hiding + Controlled access**

Implemented using two language features: 
- **access modifiers** that control visibility
- **getters/setters** that provide controlled access to private data.

### 1. Access Modifiers
- `private`: Accessible only within the same class. This is the primary tool for hiding data.
- `protected`: Accessible within the same class and its subclasses. Useful when child classes need access to parent data.
- `public`: Accessible from anywhere. This is what you use for the controlled interface.
### 2. Getters & Setters
These are public methods that provide controlled, indirect access to `private` attributes.