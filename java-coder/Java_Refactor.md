Instruction：对以下Java代码进行重构。
Context：我是一位Java开发人员，需要对一段Java代码进行重构，以提高代码质量和可维护性。代码需要满足团队的代码审核要求和高质量的代码标准。请遵循最佳实践，满足以下标准：

代码风格：

- 命名规范：使用有意义的变量名、方法名和类名。
- 使用JavaDoc中文注释，常量和接口都增加JavaDoc中文注释
- 为复杂的代码块和方法添加注释。

代码质量：

- DRY（Don't Repeat Yourself）：避免代码重复。
- 单一职责原则：每个类和方法应只有一个明确的任务。

错误处理：

- 异常处理：使用 try-catch 块来处理潜在的错误。
- 输入验证：永远不要信任用户输入，进行必要的验证。
- 日志记录：使用日志库来记录重要的运行时信息。

要求：
- 给出修改后的完整代码，Provide the full updated code.
- 如果不能一次性全部给完，可以分多次给出，If you cannot provide the full code all at once, you can provide it in multiple
parts.
- 如果你对代码有任何疑问，立刻提出来，在我澄清后再进行编写。If you have any questions about the code, please raise them
immediately, and proceed with writing after I have clarified.


Input：
```
import java.util.concurrent.Callable;
import java.util.concurrent.TimeUnit;

public class AdvancedRetryUtil {

    private int maxRetries;
    private long retryInterval;
    private long maxRetryInterval;
    private double intervalFactor;
    private Class<? extends Exception> retryOn;

    public AdvancedRetryUtil(int maxRetries, long retryInterval, long maxRetryInterval, double intervalFactor, Class<? extends Exception> retryOn) {
        this.maxRetries = maxRetries;
        this.retryInterval = retryInterval;
        this.maxRetryInterval = maxRetryInterval;
        this.intervalFactor = intervalFactor;
        this.retryOn = retryOn;
    }

    public <T> T retryTask(Callable<T> task) throws Exception {
        int retries = 0;
        long currentInterval = retryInterval;
        Exception lastException = null;

        while (retries < maxRetries) {
            try {
                return task.call();
            } catch (Exception e) {
                if (retryOn.isInstance(e)) {
                    retries++;
                    lastException = e;
                    System.out.println("Task failed, retrying... (" + retries + "/" + maxRetries + ")");
                    TimeUnit.MILLISECONDS.sleep(currentInterval);
                    currentInterval = Math.min((long) (currentInterval * intervalFactor), maxRetryInterval);
                } else {
                    throw e;
                }
            }
        }

        throw new Exception("Maximum retries reached", lastException);
    } 
}
```