# Amazon Q Developer operations assistant Workshop

## Initial Setup

Note: Before starting download the files in this repository

1. **Access AWS Console**
   - Log into your AWS Management Console
   - Ensure you're in the correct region for this workshop

2. **Deploy CloudFormation Stack**
   - Navigate to CloudFormation service
   - Click "Create stack" 
   - Select "With new resources (standard)"
   - Upload template file or paste template URL
   - Click "Next"
   - Enter stack name - aiops-workshop
   - Accept all default parameters
   - Click through configuration pages, keeping defaults
   - Acknoledge the creation of IAM resources by clicking the check box
   - Review and click "Create stack"
   - Wait for stack creation to complete (status: CREATE_COMPLETE)

3. **Access Application**
   - In the stack details, select the "Outputs" tab
   - Locate the API endpoint URL
   - Right-click and select "Open in new tab"
   - Verify you see an image of a dog (AI-generated dog with glasses)
   - Congrats! Now we are ready to break the application so we can troubleshoot

## Configure Application Signals
1. **Navigate to CloudWatch**
   - Go to the CloudWatch Console
   - Find "Application Signals" in the left navigation pane
   - Click on "Services"

2. **Enable Application Monitoring**
   - Click "Enable Application Signals"
   - Select "Lambda function" as the resource type
   - Find and select the Lambda function named "{stackname}-aiops-lambda"
   - Complete the enablement process

## Set Up Synthetic Monitoring
1. **Access Synthetics**
   - In the CloudWatch console, locate "Synthetics canary" in the left pane
   - Find "api-monitoring-canary" in the list
   - Select the checkbox next to it

2. **Start Load Test**
   - Click the "Action" button
   - Select "Start"
   - This initiates a canary that will generate load on the API

## Monitor and Investigate
1. **Wait for Alarms**
   - Allow approximately 5 minutes for the load test to generate errors

2. **Check Alarms**
   - In CloudWatch console, go to "Alarms" section
   - Filter by "In Alarm" status
   - Locate and click on the active alarm

Note: From here, you can begin your root cause analysis using CloudWatch Q Investigations for the triggered alarms.

