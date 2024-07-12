# CubeOutRotationTransformation



Cube Out Rotation Transformation with viewPager2 in android kotlin 


Code here: 

class CubeOutRotationTransformation : ViewPager2.PageTransformer {
    override fun transformPage(page: View, position: Float) {
        
        page.cameraDistance = 12000f

        when {
            position < -1 -> {

                page.alpha = 0f
            }

            position <= 0 -> {
                page.alpha = 1f
                page.pivotX = page.width.toFloat()
                page.pivotY = page.height / 2f
                page.rotationY = 90 * position
            }

            position <= 1 -> {
                page.alpha = 1f
                page.pivotX = 0f
                page.pivotY = page.height / 2f
                page.rotationY = 90 * position
            }

            else -> {
                page.alpha = 0f
            }
        }
    }
}


This helps to rotate 90 graduss degree when moving to one page to second page : I will share the result below: 

