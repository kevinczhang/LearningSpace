---
description: >-
  An event is a notification sent by an object to signal the occurrence of an
  action.
---

# Events

Events in .NET follow the observer design pattern.  In C\#, an event is an encapsulated [delegate](https://www.tutorialsteacher.com/csharp/csharp-delegates). It is dependent on the delegate. The [delegate](https://www.tutorialsteacher.com/csharp/csharp-delegates) defines the signature for the event handler method of the subscriber class.

{% hint style="info" %}
Points to Remember :

1. An event is a wrapper around a delegate. It depends on the delegate.
2. Use "event" keyword with delegate type variable to declare an event.
3. Use built-in delegate EventHandler or EventHandler&lt;TEventArgs&gt; for common events.
4. The publisher class raises an event, and the subscriber class registers for an event and provides the event-handler method.
5. Name the method which raises an event prefixed with "On" with the event name.
6. The signature of the handler method must match the delegate signature.
7. Register with an event using the += operator. Unsubscribe it using the -= operator. Cannot use the = operator.
8. Pass event data using EventHandler&lt;TEventArgs&gt;.
9. Derive EventArgs base class to create custom event data class.
10. Events can be declared static, virtual, sealed, and abstract.
11. An Interface can include the event as a member.
12. Event handlers are invoked synchronously if there are multiple subscribers.
{% endhint %}

```csharp
class Program
{
    public static void Main()
    {
        ProcessBusinessLogic bl = new ProcessBusinessLogic();
        bl.ProcessCompleted += bl_ProcessCompleted; // register with an event
        bl.StartProcess();
    }

    // event handler
    public static void bl_ProcessCompleted(object sender, ProcessEventArgs e)
    {
        Console.WriteLine("Process " + (e.IsSuccessful? "Completed Successfully": "failed"));
        Console.WriteLine("Completion Time: " + e.CompletionTime.ToLongDateString());
    }
}

public class ProcessBusinessLogic
{
    // declaring an event using built-in EventHandler
    public event EventHandler<ProcessEventArgs> ProcessCompleted; 

    public void StartProcess()
    {
        var data = new ProcessEventArgs();
		
        try
        {
            Console.WriteLine("Process Started!");
			
            // some code here..
            
            data.IsSuccessful = true;
            data.CompletionTime = DateTime.Now;
            OnProcessCompleted(data);
        }
        catch(Exception ex)
        {
            data.IsSuccessful = false;
            data.CompletionTime = DateTime.Now;
            OnProcessCompleted(data);
        }
    }

    protected virtual void OnProcessCompleted(ProcessEventArgs e)
    {
        ProcessCompleted?.Invoke(this, e);
    }
}
```

