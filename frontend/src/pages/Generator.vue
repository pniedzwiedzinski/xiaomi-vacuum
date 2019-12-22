<template>
  <div class="container">
    <h1>Xiaomi Vacuum Sound Pack Generator</h1>
    <p>
      Add your custom <code>.wav</code> files. If no file was given the default
      file from the base will be used.
    </p>
    <form
      class="form"
      :action="`${api}/generate`"
      method="POST"
      enctype="multipart/form-data"
    >
      <div>
        <label for="base">Base: </label>
        <select id="base" name="base">
          <option v-for="base in bases" :key="base" :value="base">{{
            base
          }}</option>
        </select>
      </div>
      <div v-for="field in fields" :key="field">
        <label :for="field">{{ field }} </label>
        <input :id="field" :name="field" type="file" />
      </div>
      <input type="submit" class="button" value="Generate" />
    </form>
  </div>
</template>

<script>
import "~/assets/button.css";

const fields = [
  "back_dock_failed.wav",
  "error16.wav",
  "goto_complete.wav",
  "resume_zone.wav",
  "back_dock_nearby.wav",
  "error17.wav",
  "goto_failed.wav",
  "return_no.wav",
  "bin_in.wav",
  "error18.wav",
  "home.wav",
  "return_yes.wav",
  "bin_out.wav",
  "error19.wav",
  "no_power.wav",
  "spot.wav",
  "binout_error10.wav",
  "error2.wav",
  "no_power_charging.wav",
  "start.wav",
  "bl_recovery_bootfailed.wav",
  "error21.wav",
  "no_spot_on_dock.wav",
  "stop.wav",
  "bl_recovery_failed.wav",
  "error22.wav",
  "pause.wav",
  "stop_goto.wav",
  "bl_recovery_retry.wav",
  "error23.wav",
  "pl.pkg",
  "stop_scheduled_clean.wav",
  "bl_recovery_start.wav",
  "error24.wav",
  "power_off.wav",
  "stop_spot.wav",
  "bl_recovery_updatefailed.wav",
  "error3.wav",
  "power_off_rejected.wav",
  "stop_zone.wav",
  "charging.wav",
  "error4.wav",
  "power_resume_clean.wav",
  "sysupd_complete.wav",
  "clean_bin.wav",
  "error5.wav",
  "relocate_failed.wav",
  "sysupd_failed.wav",
  "clean_finish.wav",
  "error6.wav",
  "remote.wav",
  "sysupd_notready.wav",
  "error1.wav",
  "error7.wav",
  "remote_complete.wav",
  "sysupd_start.wav",
  "error10.wav",
  "error8.wav",
  "restart_backtodock_ignore_forbidden_zone.wav",
  "sysupd_wip.wav",
  "error11.wav",
  "error9.wav",
  "restart_clean.wav",
  "timed_clean.wav",
  "error12.wav",
  "error_internal.wav",
  "restart_clean_ignore_forbidden_zone.wav",
  "wifi_reset.wav",
  "error13.wav",
  "findme.wav",
  "restart_spot_ignore_forbidden_zone.wav",
  "zone.wav",
  "error14.wav",
  "finish.wav",
  "resume_clean.wav",
  "zone_complete.wav",
  "error15.wav",
  "goto.wav",
  "resume_home.wav",
  "zone_failed.wav"
].sort();

const bases = ["pl"];

export default {
  metaInfo: {
    title: "Generator"
  },
  data() {
    return {
      fields,
      bases,
      currentBase: "pl",
      api: "http://localhost:3000"
    };
  }
};
</script>

<style scoped>
.container {
  margin: 10px;
}

.form {
  display: flex;
  flex-direction: column;
}
</style>
