---
title: "My Markdown Page title"
---
# My Markdown page

This is a Markdown page with xtra content

java script:

```java title="src/main/java/com/mycompany/myapp/MyClass.java"
package com.example;

import com.arondor.common.management.mbean.annotation.*;
import com.fast2.model.context.PatternResolver;
import com.fast2.model.punnet.ContentContainer;
import com.fast2.model.punnet.Document;
import com.fast2.model.punnet.Punnet;
import com.fast2.model.task.TaskException;
import com.fast2.model.task.annotation.TaskType;
import com.fast2.model.task.annotation.TaskType.Type;
import com.fast2.task.common.BasicTask;

@TaskType(...)                           // Source, ContentSource, Credentials, Loader, Transformer, Converter
@Description("...")                      // can be used for keyword search in catalog
public class MyTask extends BasicTask
{
    @Description("Label of field")
    @LongDescription("Helper text when field is focused")
    @Example("Used for the documentation")
    @DefaultValue("The default value")    // Automatically filled value
    @Mandatory                            // Show field for basic task configuration
    @Password                             // Hide input when filling field
    private String myTaskVariable = "The default value";


    @Override
    public boolean runTask(Punnet punnet) throws TaskException
    {
        if(myTaskVariable == null)
            throw new TaskException("Missing value for ...");

        for(Document document: punnet.getDocuments()){
            // Iterate on documents embedded by the punnet
        }

        return true;
    }

    @Override
    public synchronized void finishTask()
    {
    }

    public void setMyTaskVariable(String myTaskVariable)
    {
        this.myTaskVariable = myTaskVariable;
    }

    public String getMyTaskVariable()
    {
        return this.myTaskVariable;
    }
}

```


this is an [internal link](/blog), whereas this one is [an external link](http://Fast2.tech).