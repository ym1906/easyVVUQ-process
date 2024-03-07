(
    tfcoil_variables.jwdgcrt,
    vdump,
    tfcoil_variables.tmargtf,
) = self.supercon(
    tfcoil_variables.acstf,
    aturn,
    tfcoil_variables.bmaxtfrp,
    tfcoil_variables.vftf, ! constant result can't analyse (adjust vdalw)
    tfcoil_variables.fcutfsu, !No coreelation
    tfcoil_variables.cpttf,! No correlation
    tfcoil_variables.jwptf,! No correlation
    tfcoil_variables.i_tf_sc_mat,
    tfcoil_variables.fhts,
    tfcoil_variables.tdmptf, ! no correlation
    tfes,
    tfcoil_variables.tftmp, !vary
    tfcoil_variables.tmaxpro,
    tfcoil_variables.bcritsc,
    tfcoil_variables.tcritsc,
    output=output,
)


real(dp) :: acstf
!! Cable space area (per turn)  [m2]
!! Includes the area of voids and central helium channel
!! NOT IN DEMO INPUT FILE

real(dp) :: bmaxtfrp
!! peak field at TF conductor with ripple (T)
!! NOT IN DEMO INPUT FILE

  real(dp) :: vftf
  !! coolant fraction of TFC 'cable' (`i_tf_sup=1`), or of TFC leg (`i_tf_ssup=0`)
!! IN DEMO INPUT FILE

 real(dp) :: fcutfsu
  !! copper fraction of cable conductor (TF coils)
  !! (iteration variable 59)
!! IN DEMO INPUT ITERATION VARIABLE

  real(dp) :: cpttf
  !! TF coil current per turn (A). (calculated for stellarators) (calculated for
  !! integer-turn TF coils `i_tf_turns_integer=1`) (`iteration variable 60`)
!! IN DEMO INPUT FILE ITERATION VARIABLE

  real(dp) :: jwptf
  !! winding pack engineering current density (A/m2)
!! IN DEMO INPUT FILE AS CONTRAINT 35

  real(dp) :: fhts
  !! technology adjustment factor for critical current density fit for isumat..=2
  !! Bi-2212 superconductor, to describe the level of technology assumed (i.e. to
  !! account for stress, fatigue, radiation, AC losses, joints or manufacturing
  !! variations; 1.0 would be very optimistic)
!! NOT IN DEMO FILE

  real(dp) :: tftmp
  !! peak helium coolant temperature in TF coils and PF coils (K)
tftmp = 4.750
!! IN DEMO FILE

  real(dp) :: tmaxpro
  !! maximum temp rise during a quench for protection (K)
!! NOT IN DEMO FILE

    tfcoil_variables.bcritsc,
    tfcoil_variables.tcritsc,
  real(dp) :: bcritsc
  !! upper critical field (T) for Nb3Sn superconductor at zero temperature and
  !! strain (`i_tf_sc_mat=4, =bc20m`)
  real(dp) :: tcritsc
  !! critical temperature (K) for superconductor at zero field and strain (`i_tf_sc_mat=4, =tc0m`)
!! NOT IN DEMO FILE
