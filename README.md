# cfn-modules: AWS Route53 hosted zone (private)

AWS Route53 hosted zone accessible inside VPC only. For a public accessible hosted zone look at the [route53-hosted-zone-public](https://www.npmjs.com/package/@cfn-modules/route53-hosted-zone-public) module.

## Install

> Install [Node.js and npm](https://nodejs.org/) first!

```
npm i @cfn-modules/route53-hosted-zone-private
```

## Usage

```
---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'cfn-modules example'
Resources:
  Function:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      Parameters:
        VpcModule: !GetAtt 'Vpc.Outputs.StackName' # required
        Name: 'local.widdix.de' # required
      TemplateURL: './node_modules/@cfn-modules/route53-hosted-zone-private/module.yml'
```

## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>VpcModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/vpc">vpc module</a></td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>The name of the domain (hosted zone)</td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
  </tbody>
</table>
