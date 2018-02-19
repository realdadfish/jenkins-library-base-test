@Library('jenkins-library-base')
import com.ibm.oip.jenkins.*;
import com.ibm.oip.jenkins.steps.*;
import com.ibm.oip.jenkins.steps.java.*;

Pipeline master = new PipelineBuilder().forMaster().withSteps([
Common.PARALLEL(
  new Step(){
    void doStep(BuildContext buildContext) {
        buildContext.getScriptEngine().sh "echo 'step 1'"
   }
  },
     new Step(){
    void doStep(BuildContext buildContext) {
        buildContext.getScriptEngine().sh "echo 'step 2'"
   }
   },
   new Step(){
    void doStep(BuildContext buildContext) {
        buildContext.getScriptEngine().sh "echo 'step 3'"
   }
  }
)]).build();

new PipelineRunner()
  .withScriptEngine(this)
  .withBranch("master")
  .withPossiblePipelines(master)
  .run();

