

pipeline{
agent any
parameters {

booleanParam(name:'hello',defaultValue:'true',description:'checking the booleanvalue')
}

stages{
stage('test') {
steps{

script {

if(hello)
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
