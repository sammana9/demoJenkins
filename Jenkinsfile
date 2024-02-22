

pipeline{
agent any
parameters {

booleanParam(name:'hello',defaultValue:'false',description:'checking the booleanvalue')
}

stages{
stage('test') {
steps{

script {

if(params.hello)
{
echo 'value is true'
}
else
{
 echo 'value is false'
}

}
}

}
}
}
