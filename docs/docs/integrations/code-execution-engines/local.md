---
sidebar_position: 3
---

# Local (Computer-Use)

`CommandLineExecutionEngine` uses the local computer env to execute provided command line code.
There are `CommandLineTool` and `LocalScriptExecutionTool` two implemented tools,
that can be useful for **Desktop Automation** or **Computer-Use** Agents
(such as File Management, Application Control). You can control your computer using natural language, something like:
 - `set my mac output volume 50`
 - `list all running applications in my mac`
 - `tell a story and then read it out loud`
 - `tell a story about moon and save it into a text file`
 - ...

Attention! It might be *dangerous* to execute the code in a production online serving environment.
It needs to be executed through security sandbox environment if used in online serving.

## Maven Dependency

```xml
<dependency>
    <groupId>dev.langchain4j</groupId>
    <artifactId>langchain4j-code-execution-engine-local</artifactId>
    <version>1.9.0-beta16-SNAPSHOT</version>
</dependency>
```

## APIs

- `CommandLineExecutionEngine`
- `CommandLineTool`
- `LocalScriptExecutionTool`


## Examples

```java
        LocalScriptExecutionTool tool = new LocalScriptExecutionTool();

        Assistant assistant = AiServices.builder(Assistant.class)
                .chatModel(model)
                .tools(tool)
                .chatMemory(MessageWindowChatMemory.withMaxMessages(10))
                .build();

        String answer = assistant.chat("list all running applications in my mac");
        System.out.println(answer);
```

- [CommandLineExecutionEngineTest](https://github.com/langchain4j/langchain4j/blob/main/code-execution-engines/langchain4j-code-execution-engine-local/src/test/java/dev/langchain4j/code/local/CommandLineExecutionEngineTest.java)
- [CommandLineToolIT](https://github.com/langchain4j/langchain4j/blob/main/code-execution-engines/langchain4j-code-execution-engine-local/src/test/java/dev/langchain4j/agent/tool/local/CommandLineToolIT.java)
- [CommandLineToolTest](https://github.com/langchain4j/langchain4j/blob/main/code-execution-engines/langchain4j-code-execution-engine-local/src/test/java/dev/langchain4j/code/local/CommandLineToolTest.java)
- [LocalScriptExecutionToolIT](https://github.com/langchain4j/langchain4j/blob/main/code-execution-engines/langchain4j-code-execution-engine-local/src/test/java/dev/langchain4j/agent/tool/local/LocalScriptExecutionToolIT.java)
- [LocalScriptExecutionToolTest](https://github.com/langchain4j/langchain4j/blob/main/code-execution-engines/langchain4j-code-execution-engine-local/src/test/java/dev/langchain4j/agent/tool/local/LocalScriptExecutionToolTest.java) 
